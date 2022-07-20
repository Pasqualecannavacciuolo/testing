<script setup>
</script>

<template>
    <div class="container">
        <div class="row row-cols-1 row-cols-md-3 g-4">
            <div v-for="card in 10" key="card" class="col">
                <div class="card h-100">
                    <img src="https://lifeunited.org/wp-content/uploads/2022/02/efficient-random-word-generator.jpg"
                        class="card-img-top" alt="random image">
                    <div class="card-body">
                        <h5 class="card-title">Card title</h5>
                        <p class="card-text">Some quick example text to build on the card title and make up the bulk of
                            the
                            card's
                            content.</p>
                        <a href="#" class="btn btn-primary">Go somewhere</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>