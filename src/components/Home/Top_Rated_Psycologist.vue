<script>
import { onMounted } from 'vue'

export default {
    data() {
        return {
            top_rated_psycologist: [
                {
                    nome: 'Pasquale Cannavacciuolo',
                    specializzazione: 'Trauma infantile',
                    indice_gradimento: 4.7,
                    immagine: '@/assets/pako_doctor.png',
                    premi: [
                        {
                            nome: 'Professionista premiato',
                            immagine_premio: '../../../src/assets/reward.png'
                        },
                        {
                            nome: 'Disponibile online',
                            immagine_premio: '../../../src/assets/smartphone.png'
                        },
                        {
                            nome: 'Amato dai pazienti',
                            immagine_premio: '../../../src/assets/medal.png'
                        }
                    ]
                },
                {
                    nome: 'Maria giovanna Guadagno',
                    specializzazione: 'Disturbo cognitivo del linguaggio',
                    indice_gradimento: 4.9,
                    immagine: '../../../src/assets/female_doctor.png',
                    premi: [
                        {
                            nome: 'Professionista premiato',
                            immagine_premio: '../../../src/assets/reward.png'
                        },
                        {
                            nome: 'Disponibile online',
                            immagine_premio: '../../../src/assets/smartphone.png'
                        },
                        {
                            nome: 'Amato dai pazienti',
                            immagine_premio: '../../../src/assets/medal.png'
                        },
                        {
                            nome: 'Migliori recensioni',
                            immagine_premio: '../../../src/assets/star.png'
                        }
                    ]
                },
                {
                    nome: 'Vincenzo Pugliese',
                    specializzazione: 'PSD e traumi di guerra',
                    indice_gradimento: 4.8,
                    immagine: '../../../src/assets/vincenzo_doctor.png',
                    premi: [
                        {
                            nome: 'Professionista premiato',
                            immagine_premio: '../../../src/assets/reward.png'
                        },
                        {
                            nome: 'Disponibile online',
                            immagine_premio: '../../../src/assets/smartphone.png'
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
                                <img :src="premio.immagine_premio" alt="immagine premio">
                            </span>
                        </div>
                    </small>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
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

.psycologist-card img {
    width: 250px;
    height: 250px;
    background-position: center;
    background-size: contain;
}

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