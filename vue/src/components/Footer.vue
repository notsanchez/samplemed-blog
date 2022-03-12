<template>
  <div class="nav-bar">
    <nav class="navbar navbar-expand-lg nav-1">
      <div class="container mw-3 px-3">
        <a class="navbar-brand" href="https://www.samplemed.com.br/">
        Tecnologia
        </a>
        <div class="linha-vertical"></div>
        <a class="navbar-brand" href="https://www.samplemed.com.br/">
        Atualidade
        </a>
        <div class="linha-vertical"></div>
        <a class="navbar-brand" href="https://www.samplemed.com.br/">
        Esporte
        </a>
        <div class="linha-vertical"></div>
        <a class="navbar-brand" href="https://www.samplemed.com.br/">
        Pandemia
        </a>
      </div>
    </nav>
    <nav class="second navbar navbar-expand-lg nav-1">
      <div class="image container mw-0 px-3">
        <h6>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus volutpat bibendum neque, non tempus mauris ultrices eu. Nulla ex enim, mollis quis tellus ac, imperdiet dictum metus. Duis et interdum nisl. Aenean ut libero a dolor vehicula efficitur. Curabitur id ultricies augue.</h6>
      </div>
    </nav>
    <nav class="second navbar navbar-expand-lg nav-1">
      <div class="container mw-0 px-3">
        <h5>©2022 Copyright: Samplemed</h5>
      </div>
    </nav>
  </div>
</template>

<script>
  import { mapState } from 'vuex'
  export default {
    name: 'SecondNavbar',
    computed: mapState(['accessToken'])
  }
</script>

<style scoped>

.navbar {
  background-color: rgba(148, 148, 148, 0.445);
}

.image {
    display: grid!important;
}


.second {
  background-color: rgba(77, 77, 77, 0.445);
}

h5{
    color: rgb(255, 255, 255);
}

h6{
    text-align: center;
    padding: 30px;
    color: rgba(255, 255, 255, 0.829);
}

.container{
    justify-content: center!important;
}



</style>