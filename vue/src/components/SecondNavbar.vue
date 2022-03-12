<template>
  <div class="nav-bar">
    <nav class="navbar navbar-expand-lg nav-1">
      <div class="container mw-0 px-3">
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
  background-color: rgba(20, 20, 20, 0.822);
  border-bottom-right-radius: 25px;
  border-bottom-left-radius: 25px;
}

.navbar-brand {
  transition: all 0.2s;
}

.navbar-brand:hover{
  transform: scale(1.05);
  color: rgba(156, 102, 207, 0.712)!important;
}

.linha-vertical {
  height: 8px;
  border-left: 2px solid;
  padding: 10px;
}


</style>