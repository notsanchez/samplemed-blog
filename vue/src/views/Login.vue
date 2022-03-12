<template>
  <div>
  <div class="container text-dark">
    <div class="row justify-content-md-center">
      <div class="container-general col-md-5 p-3 login justify-content-md-center">

        <img src="../assets/brand-name.png" width="" height="57" class="samplemed_logo" alt="">

        <h1 class="space"></h1>
        

        <p v-if="incorrectAuth">Username ou senha incorretos - tente novamente.</p>
        <form v-on:submit.prevent="login">
          <div class="form-group">
            <input type="text" name="username" id="user" v-model="username" class="form-control" placeholder="Username">
          </div>
          <div class="form-group">
            <input type="password" name="password" id="pass" v-model="password" class="form-control" placeholder="Password">
          </div>
          <button type="submit" class="btn btn-lg btn-block">Login</button>

          <div class="div-links text-xs-center justify-center"> 
            <a class="create-account h7 mb-1" href="">Criar conta</a>
            <a class="esqueceu-senha h7 mb-1" href="">Esqueceu sua senha?</a>
          </div>
          
        </form>
        
      </div>
    </div>
  </div>
  </div>
</template>

<script>
  export default {
    name: 'login',
    data () {
      return {
        username: '',
        password: '',
        incorrectAuth: false
      }
    },
    methods: {
      login () { 
        this.$store.dispatch('userLogin', {
          username: this.username,
          password: this.password
        })
        .then(() => {
          this.$router.push({ name: 'posts' })
        })
        .catch(err => {
          console.log(err)
          this.incorrectAuth = true
        })
        }
      }
  }
</script>

<style>
body { 
  background-color:rgb(26, 26, 26)!important;
}
  .login{
    background-color:rgb(19, 19, 19);
    margin-top: 20%;
    box-shadow: 0 0px 18px 0 rgba(80, 0, 100, 0.137), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
  input {
    padding: 25px 10px;
}

p {
    color: rgb(248, 63, 63);
}

.samplemed_logo {
  position: relative;
  left: 25px;
  top: 20px;
}

a:hover{
  text-decoration: none!important;
}

.container-general {
  height: 470px;
  box-shadow: #000000;
  border-radius: 20px;
}

.space {
  padding-top: 70px;
  padding-bottom: 30px;
}

.btn {
  background-color: rgb(102, 23, 155)!important;
  color: azure!important;
  transition: all 0.3s!important;
}

.btn:hover {
  transform: scale(1.05);
  background-color: rgb(66, 15, 100)!important;
}

.create-account {
  padding-left: 185px;
  padding-top: 30px;
  position: absolute;
  transition: all 0.2s;
}

.create-account:hover{
  color: rgb(151, 151, 151)!important;
}

.esqueceu-senha {
  padding-left: 150px;
  padding-top: 20px;
  position: relative;
  transition: all 0.2s;
}

.esqueceu-senha:hover{
  color: rgb(151, 151, 151)!important;
}

.div-links {
  padding-top: 12px;
}


</style>