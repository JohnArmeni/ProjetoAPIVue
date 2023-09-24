<script setup>
const times = defineProps(["full_name", "name", "id", "abbreviation", "city" ])
const img = `../src/assets/logo/${times.id}.png`

</script>

<template>
    <div class="col-2"> 
        <div class="card mb-3 border-0 mh-100 d-inline-block">
            <img class="card-img-top" :src="img" alt="Card image cap" style="max-height: 150px; min-height: 150px;">
            <div class="card-body">
                <h5 class="card-title">{{ times.name }}</h5>
                <a :href="'/informacoes?time=' + times.id" target= "/informacoes" class="btn btn-primary">Detalhes</a>
            </div>           
        </div>
    </div>

</template>

<style> 

</style>