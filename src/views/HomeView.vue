<script setup>
import { capitalize, onMounted, reactive, ref } from 'vue';
import ListaTimes from '../components/ListaTimes.vue';

let baseUrlSvg = ref("https://raw.githubusercontent.com/PokeApi/sprites/master/sprites/pokemon/other/dream-world");
let times = reactive(ref());

onMounted(() =>{
  fetch("https://www.balldontlie.io/api/v1/teams/")
  .then(response => response.json())
  .then(response => {
    times.value = response.data;
    console.log(response);
  })
})

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-6">
        <div class="col-sm-12 col-md-6" >
          <div class="card" style="width: 18rem;">
            <img src="src\assets\Nba_logo_PNG1.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">BallDontLie</h5>
              <p class="card-text">É uma API criada de forma gratuita para consulta de times da NBA League, com fins didáticos. Ao lado, temos os times e informações. Clique e confira.</p>
              
            </div>
          </div>
          
        </div>
        <div class="col-sm-12 col-md-6" >
          <div class="card">
            <div class="card-body row">
            <ListaTimes
            v-for="time in times"
            :key="time.name"
            :name="time.full_name"
            />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

