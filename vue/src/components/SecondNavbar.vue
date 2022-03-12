<template>
  <div class="nav-bar">
    <nav class="navbar navbar-expand-lg nav-1">
      <div class="container mw-0 px-3">

        <a class="navbar-brand" href="https://www.samplemed.com.br/">
        <img src="../assets/brand-name.png" width="" height="37" class="d-inline-block align-top" alt="">
        </a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto">
            <li class="nav-item">
            <li class="nav-item" v-if="accessToken!=null"><router-link :to = "{ name:'logout' }">Log out</router-link></li>
          </ul>
        </div>

      </div>
    </nav>
  </div>
</template>

<script>
  import { mapState } from 'vuex'
  export default {
    name: 'Navbar',
    computed: mapState(['accessToken'])
  }
</script>

<style scoped>
    a {
      color:rgb(255, 255, 255);
  }

.navbar {
  background-color: rgb(12, 12, 12);
}

.navbar-brand {
  padding-left: 450px;
}

.nav-item {
  overflow:hidden;
  white-space: nowrap;
  padding-left: 350px;
}

</style>