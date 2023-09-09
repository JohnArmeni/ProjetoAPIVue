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
    <div class="container-fluid">
      <div class="card" style="width: 18rem;">
        <img src="..." class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>
  </main>
</template>
