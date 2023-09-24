<script setup>
import { capitalize, onMounted, reactive, ref } from 'vue';
import ListaTimes from '../components/ListaTimes.vue';


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
      <div class="row mt-5">
        <div class="col-sm-6 col-md-3" >
          <div class="card border-0" style="width: 18rem;">
            <img src="src\assets\cryingjordan.jpg" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">BallDontLie</h5>
              <p class="card-text">É uma API criada de forma gratuita para consulta de times da NBA League, com fins didáticos. Ao lado, temos os times e informações. Clique e confira.</p>
              
            </div>
            
          </div>
          <img src="src\assets\Nba_logo_PNG1.png" class="img-thumbnail mt-5 border-0" alt="...">
        </div>
        <div class="col-sm-18 col-sm">
          <div class="card border-0">
            <div class="card-body row">
            <ListaTimes
            v-for="time in times"
            :key="time.full_name"
            :name="time.name"
            :id="time.id"
            />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

