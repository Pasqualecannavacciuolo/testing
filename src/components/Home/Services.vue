<script>

</script>

<template>
    <div v-motion
  :initial="{
    y: 100,
    opacity: 0,
  }"
  :enter="{
    y: 0,
    opacity: 1,
    transition: {
      type: 'spring',
      stiffness: 250,
      damping: 25,
      mass: 0.5,
    },
  }" class="row jumbotron-text mt-5">
        <div class="col">
            <div class="p-5 mb-4 rounded-3 jumbotron-text">
                <h1>Cosa imparerai</h1>
                <div class="row row-cols-1 row-cols-md-2 g-4 mt-5">
                    <div class="col">
                        <div class="card">
                            <img src="@/assets/combatti.png" class="card-img-top" alt="combatti le tue paure">
                            <div class="card-body">
                                <h5 class="card-title">Combatti le tue paure</h5>
                                <p class="card-text">This is a longer card with supporting text below as a natural
                                    lead-in to additional content. This content is a little bit longer.</p>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="card">
                            <img src="@/assets/conosciti.png" class="card-img-top" alt="conosciti">
                            <div class="card-body">
                                <h5 class="card-title">Impara a conoscerti</h5>
                                <p class="card-text">This is a longer card with supporting text below as a natural
                                    lead-in to additional content. This content is a little bit longer.</p>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="card">
                            <img v-motion-roll-visible-top src="@/assets/nutri.png" class="card-img-top" alt="nutri la tua mente">
                            <div class="card-body">
                                <h5 class="card-title">Nutri la tua mente</h5>
                                <p class="card-text">This is a longer card with supporting text below as a natural
                                    lead-in to additional content.</p>
                            </div>
                        </div>
                    </div>
                    <div class="col">
                        <div class="card">
                            <img v-motion-roll-visible-top src="@/assets/amati.png" class="card-img-top" alt="amati">
                            <div class="card-body">
                                <h5 class="card-title">Impara ad amarti</h5>
                                <p class="card-text">This is a longer card with supporting text below as a natural
                                    lead-in to additional content. This content is a little bit longer.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.card-img-top {
    margin: auto auto;
    background-position: center;
    background-size: cover;
    width: 150px;
    height: 150px;
}
.card {
    border: none;
}

 

</style>