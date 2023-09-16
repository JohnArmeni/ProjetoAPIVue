<script setup>
const times = defineProps(["full_name", "name" ])

</script>

<template>
    <div class="col-4"> 
        <div class="card mb-3">
            

            <div class="card-body">
                <h5 class="card-title">{{ times.name }}</h5>
                <a :href="times.full_name" target= "_blank" class="btn btn-primary">Detalhes</a>
            </div>           
        </div>
    </div>

</template>

<style> 

</style>