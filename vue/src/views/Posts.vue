<template>
  <div class="posts">
    <NavBar></NavBar>
    <SecondNavBar></SecondNavBar>
      <div class="background album py-5" style="padding-bottom:250px!important">
          <div class="container">
            <div class="row">
              <div v-for="posts in APIData" :key="posts.id" class="col-md-12">
                <div class="mb-4 box-shadow">
                  <div class="card-body">
                      <h4 class="title"><a class="" href="https://www.globo.com/">{{posts.title}}</a></h4>
                      <span class="card-text">{{posts.content}}</span>
                      <div class="d-flex justify-content-between align-items-center">
                      <div class="btn-group">                     
                      </div>
                      <small class="text-muted">A alguns minutos...</small>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
      </div>
      <Footer></Footer>
  </div>
</template>

<script>
  import NavBar from '../components/Navbar.vue'
  import Footer from '../components/Footer.vue'
  import SecondNavBar from '../components/SecondNavbar.vue'
  import { getAPI } from '../axios-api'
  import { mapState } from 'vuex'
  export default {
    name: 'Posts',
    onIdle () {
      this.$store.dispatch('userLogout')
        .then(() => {
          this.$router.push({ name: 'login' })
        })
    },
    components: {
      NavBar,
      SecondNavBar,
      Footer,
    },
    computed: mapState(['APIData']),
    created () {
        getAPI.get('/posts/', { headers: { Authorization: `Bearer ${this.$store.state.accessToken}` } })
          .then(response => {
            this.$store.state.APIData = response.data
          })
          .catch(err => {
            console.log(err)
          })
    }
  }
</script>

<style>

.card-body {
  background-color: rgb(12, 12, 12);
  border-radius: 10px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

a{
  color: rgb(255, 255, 255)!important;
}

span{
  color: rgb(214, 214, 214)!important;
}


::-webkit-scrollbar {
    width: 6px;
    height: 6px;
}

::-webkit-scrollbar-track { 
    -webkit-border-radius: 16px;
    border-radius: 6px;
}

::-webkit-scrollbar-thumb {
    -webkit-border-radius: 16px;
    border-radius: 6px;
    background: rgb(102, 23, 155);  
}

.background{
  padding-bottom: 200px!important;
}

</style>