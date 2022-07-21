<script>
export default {
    data() {
        return {
            top_rated_psycologist: [
                {
                    nome: 'Pasquale Cannavacciuolo',
                    specializzazione: 'Trauma infantile',
                    indice_gradimento: 4.7,
                    immagine: 'https://images.unsplash.com/photo-1522075469751-3a6694fb2f61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTd8fHBvcnRyYWl0fGVufDB8fDB8fA%3D%3D&w=1000&q=80',
                    premi: [
                        {
                            nome: 'Professionista premiato',
                        },
                        {
                            nome: 'Disponibile online',
                        },
                        {
                            nome: 'Amato dai pazienti',
                        }
                    ]
                },
                {
                    nome: 'Maria giovanna Guadagno',
                    specializzazione: 'Disturbo cognitivo del linguaggio',
                    indice_gradimento: 4.9,
                    immagine: 'https://images.unsplash.com/photo-1597223557154-721c1cecc4b0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTF8fGZhY2UlMjBwb3J0cmFpdHxlbnwwfHwwfHw%3D&w=1000&q=80',
                    premi: [
                        {
                            nome: 'Professionista premiato',
                        },
                        {
                            nome: 'Disponibile online',
                        },
                        {
                            nome: 'Amato dai pazienti',
                        },
                        {
                            nome: 'Migliori recensioni',
                        }
                    ]
                },
                {
                    nome: 'Vincenzo Pugliese',
                    specializzazione: 'PSD e traumi di guerra',
                    indice_gradimento: 4.8,
                    immagine: 'https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MzZ8fHBvcnRyYWl0fGVufDB8fDB8fA%3D%3D&w=1000&q=80',
                    premi: [
                        {
                            nome: 'Professionista premiato',
                        },
                        {
                            nome: 'Disponibile online',
                        }
                    ]
                }
            ]
        }
    }, // Fine di data()
    mounted() {
        // Serve per dare l'animazione e lo stile ai TOOLTIP di Bootstrap
        let tooltip = document.querySelectorAll('.tt');
        tooltip.forEach(t => {
            new bootstrap.Tooltip(t);
        });
    }
}

</script>

<template>
    <div class="row mt-5 p-5 top-rated">
        <h1>I migliori professionsti sulla piattaforma</h1>
        <div class="card-group">
            <div class="card psycologist-card" v-for="psycologist in top_rated_psycologist" key="card">
                <img :src="psycologist.immagine" class="card-img-top"
                    alt="immagine psicologo tra i migliori sulla piattaforma">
                <div class="card-body">
                    <h5 class="card-title">{{ psycologist.nome }}</h5>
                    <p class="card-text">
                        <p class="p_light">Campo di competenza</p>
                        <strong>{{ psycologist.specializzazione }}</strong>
                        
                    </p>
                    <small>
                        Indice di gradimento:
                        <strong>{{ psycologist.indice_gradimento }}/5</strong>
                    </small>
                </div>
                <div class="card-footer">
                    <small class="badges">
                        <div class="badge text-dark" v-for="premio in psycologist.premi">
                            <span class="tt" data-bs-placement="top" :title="premio.nome">
                                <img v-if="premio.nome === 'Professionista premiato'" src="@/assets/reward.png" alt="immagine premio">
                                <img v-else-if="premio.nome === 'Disponibile online'" src="@/assets/smartphone.png" alt="immagine premio">
                                <img v-else-if="premio.nome === 'Amato dai pazienti'" src="@/assets/medal.png" alt="immagine premio">
                                <img v-else-if="premio.nome === 'Migliori recensioni'" src="@/assets/star.png" alt="immagine premio">
                            </span>
                        </div>
                    </small>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.p_light {
    font-weight: 200;
    text-align: center;
}

.top-rated {
    background-color: #fff;
}

.card-group {
    margin-top: 7em;
    gap: 5em;
}

.psycologist-card {
    text-align: center;
}

.card-img-top {
    margin: auto auto;
    background-position: center;
    background-size: cover;
    width: 250px;
    height: 250px;
}

.psycologist-card img {
    margin: auto auto;
    width: 250px;
    height: 250px;
    background-position: center;
    background-size: cover;
}*/

.card-footer {
    border-top: none;
    background-color: #fafafa;
}

.badges {
    display: flex;
    flex-direction: row;
    justify-content: center;
    height: 45px;
}

.badge img {
    width: 50px;
    height: 45px;
}

@media (max-width: 575.98px) { 
    .card-text {
        text-align: center;
    }
    .p_light {
        font-size: .9em !important;
        margin-top: 1em;
        margin-bottom: 0;
        padding-bottom: 0;
    }
    
}
</style>