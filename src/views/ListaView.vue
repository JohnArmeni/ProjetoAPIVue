<script>
import ListaTimes from '../components/ListaTimes.vue';

import { onMounted, ref } from 'vue';

export default {
  setup() {
    const times = ref([]); // Inicialize a variável reativa para armazenar os dados da equipe
    
    onMounted(() => {
      const urlParams = new URLSearchParams(window.location.search);
      const id = urlParams.get('time');

      // Certifique-se de que "id" seja definido antes de fazer a chamada da API
      if (id) {
        // Realize a chamada da API somente quando houver um "id" válido
        fetch("https://www.balldontlie.io/api/v1/teams/" + id)
          .then(response => response.json())
          .then(response => {
            times.value = response;
            console.log(times.value);
            
          })
          .catch(error => {
            console.error("Erro na chamada da API:", error);
          });
      } else {
        console.error("ID inválido ou ausente na URL");
      }
    });

    return {
      times
    };
  }
};



</script>

<template>
<ul class="list-group mt-5">
    <li class="list-group-item shadow-sm p-2 mb-3 bg-white rounded border-top-0" >
       <h3 class="text-primary">ID:</h3> {{ times.id }}
    </li>
    <li class="list-group-item shadow-sm p-2 mb-3 bg-white rounded" >
      <h3 class="text-primary">Nome:</h3> {{ times.name}}
    </li>
    <li class="list-group-item shadow-sm p-2 mb-3 bg-white rounded" >
      <h3 class="text-primary">Nome Completo:</h3> {{ times.full_name }}
    </li>
    <li class="list-group-item shadow-sm p-2 mb-3 bg-white rounded" >
      <h3 class="text-primary">Sigla:</h3> {{ times.abbreviation }}
    </li>
    <li class="list-group-item shadow-sm p-2 mb-3 bg-white rounded" >
      <h3 class="text-primary">Cidade de origem:</h3> {{ times.city }}
    </li>
  
</ul>
<div class="img">
  <img src="src\assets\cryingjordan.jpg" class="img-thumbnail border-0 rounded float-left" alt="..." style="width:200px; height:200px">
  <h5>Don't cry, Jordan</h5>
</div>



</template>