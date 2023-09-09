<script setup>
import {ref} from 'vue'
let num = ref(0);
</script>


<template>
  <nav class="navbar navbar-expand-lg static-top fixed-top" style="background-color: lightgreen;">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">ANTT Pesquisa</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
          <a class="nav-link" href="#">Busca</a>
          <a class="nav-link" href="#">Sobre</a>
          <a class="nav-link" aria-disabled="true">Quem somos</a>
        </div>
      </div>
    </div>
  </nav>


 
</template>


