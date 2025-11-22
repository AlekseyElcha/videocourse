<template>
  <div id="app"> 
    <auth-component 
      v-if="!isAuth && !isRegister" 
      @handleAuth="handleAuth"
      @handleRegister="handleRegister"
    />
    <div v-else>
      <p v-if="isAuth">Вы авторизованы</p>
      <p v-if="isRegister">Вы зарегистрированы</p>
    </div>
  </div>
</template>


<script>
import AuthComponent from './components/AuthComponents.vue'

export default {
  name: 'App',
  components: {
    AuthComponent
  },
  data(){
    return {
      isAuth: false,
      isRegister: false
    }
  },
  methods:{
    handleAuth(){
      this.isAuth = true;
    },
    handleRegister(){
      this.isRegister = true;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
