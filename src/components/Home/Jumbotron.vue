<script>
export default {
    data() {
        return {
            show: false,
            showGif: false
        }
    },
    mounted() {
        this.show = true;
        this.showGif = true
    }
}
</script>
<template>
    <div class="row row-bg mt-5 jumbotron-section">
        <transition name="slide-fade">
            <div class="col" v-if="show">
                <div class="mb-4 rounded-3 jumbotron-text">
                    <div class="container-fluid py-5 hero-text">
                        <h1 class="display-4 fw-bold">Benvenuto</h1>
                        <p class="col-md-12">
                            Hai appena affrontato il primo passo verso la serenità mentale, il primo passo rientra
                            tra gli scogli più diffusi è un pò come chiedere scusa, non è sempre facile farlo, questo
                            è il momento di chiedere scusa al tuo corpo e finalmente ricongiungerti al tuo
                            io più profondo.
                        </p>
                    </div>
                    <button class="btn btn-lg cta" type="button">Scopri i professionisti</button>
                </div>
            </div>
        </transition>
        <transition name="slide-up">
            <div class="col gif-image" v-if="showGif">
                <img src="@/assets/hero.gif" alt="hero gif">
            </div>
        </transition>
    </div>
</template>

<style>
.jumbotron-text, .row-bg {
    background-color: #fff;
}

.cta {
    background-color: #F94482;
    color: #fff;
    font-weight: 600;
}

.jumbotron-text {
    padding: 50px;
}

/** 
*   SLIDE TRANSITION FOR THE JUMBOTRON TEXT
*/
.slide-fade-enter-active {
    transition: all 1s ease-out;
}

.slide-fade-leave-active {
    transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
    transform: translateX(160px);
    opacity: 0.1;
}

/** 
*   SLIDE UP TRANSITION FOR THE GIF
*/
.slide-up-enter-active {
    transition: all 0.3s ease-out;
}

.slide-up-leave-active {
    transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-up-enter-from,
.slide-up-leave-to {
    transform: translateY(160px);
    opacity: 0.1;
}

@media (max-width: 575.98px) { 
    .gif-image img{
        max-width: 93vw;
        padding: 0;
        margin: 0;
    }
    /*.jumbotron-section {
        display: flex;
        flex-direction: column-reverse;
    }*/
    .jumbotron-text {
        margin-top: 1.3em;
        padding: 10px;
    }
    .hero-text {
        display: flex;
        flex-direction: column;
        gap: 2em;
        justify-content: center;
    }
    h1 {
        font-size: 2em !important;
        margin-bottom: 1em;
        text-align: center;
    }
    p {
        font-size: 1em !important;
        text-align: justify;
        letter-spacing: .001em;
    }
    .cta {
        margin: 0 auto;
        font-size: 1em !important;
        display: flex !important;
    }
}
</style>