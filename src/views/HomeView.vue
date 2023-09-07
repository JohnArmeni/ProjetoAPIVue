<script setup>
import { capitalize, onMounted, reactive, ref } from 'vue';

let listaSolicitacoes = reactive(ref());
onMounted(() => {
  fetch("https://dados.antt.gov.br/dataset/d46830c2-a0dc-49e2-b057-5f60f4e03094/resource/b66afac7-667b-48fd-9fae-e921f0b4c66a/download/solicitacoes_de_mercado_2023.json")
  .then(response => response.json())
  .then(response =>{
    listaSolicitacoes.value = response.results;
    console.log(response);

  })
})


</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6" >
          <div class="card" style="width: 18rem;">
            <img src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/095.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Onix</h5>
              <p class="card-text">Premier 2023/2024</p>
              
            </div>
          </div>
          <div class="card" style="width: 18rem;">
            <img src="https://garagem360.com.br/wp-content/uploads/2022/09/ChevroletOnixRS2022dianteira-1024x683-1.jpg" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Onix</h5>
              <p class="card-text">Pokemon tipo pedra</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
