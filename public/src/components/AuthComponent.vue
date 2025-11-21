<template>
    <div>
        <h2>Регистрация</h2>
        <form @submit.prevent="register">
            <div>
                <label for="registerName">Имя:</label>
                <input type="text" id="registerName" v-model="registerName"></input>
            </div>
             <div>
                <label for="registerAge">Имя:</label>
                <input type="text" id="registerAge" v-model="registerAge"></input>
            </div>
            <button type="submit">Зарегистрироваться</button>
        </form>

        <h2>Авторизация</h2>
        <form @submit.prevent="login">
            <div>
                <label for="loginName">Имя:</label>
                <input type="text" id="loginName" v-model="registerName"></input>
            </div>
            <button type="submit">авторизоваться</button>
        </form>
    </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'AuthComponent',
  data(){
    return {
      registerName: '',
      registerAge: '',
      loginNam: ''

    }
  },
  methods:{
    async register(){
        const response = await axios.post('http://127.0.0.1:8000/users/', {
            name: this.registerName,
            age: this.registerAge
        });

        console.log('Register success:' + response.data)
    },
    async login() {

    }
  }
}
</script>

<style>
</style>
