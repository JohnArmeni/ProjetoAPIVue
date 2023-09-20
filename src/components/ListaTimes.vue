<script setup>
const times = defineProps(["full_name", "name", "id", "abbreviation", "city" ])

</script>

<template>
    <div class="col-2"> 
        <div class="card mb-3 border-0">
            <div class="card-body">
                <h5 class="card-title">{{ times.name }}</h5>
                <a :href="'/informacoes?time=' + times.id" target= "/informacoes" class="btn btn-primary">Detalhes</a>
            </div>           
        </div>
    </div>

</template>

<style> 

</style>