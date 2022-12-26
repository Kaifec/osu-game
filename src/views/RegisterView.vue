<template>
    <input v-model="login" placeholder="Логин">
    <input v-model="password" placeholder="Пароль">
    <button @click="regUser">Регистрация</button>
  </template>
  
  
  <script>
  export default {
    data: () => ({
    login: '',
    password: '',
  }),
    methods: {
        regUser() {
            this.fetchReg()
        },
        fetchReg() {
            fetch('http://localhost:5000/api/register', {
                method: 'POST',
                body: JSON.stringify({
                    login: this.login, password: this.password
                }),
                headers: {
                    "Content-Type": "application/json"
                }
            })
        }
    }
  }
  </script>