<template>
    <input v-model="login" placeholder="Логин">
    <input v-model="password" placeholder="Пароль">
    <button @click="loginUser">Авторизироваться</button>
</template>


<script>
import cookie from "js-cookie"
export default {
    data: () => ({
    login: '',
    password: ''
}),
    methods: {
        loginUser() {
            this.fetchLogin()
          this.$router.push("/game")
        },
        fetchLogin() {
            fetch('http://localhost:5000/api/login', {
                method: 'POST',
                body: JSON.stringify({
                    login: this.login, password: this.password
                }),
                headers: {
                    "Content-Type": "application/json"
                }
            }).then(response => response.json())
            .then(data => {
                // if empty response say that login or password is incorrect unless set cookie
                if (data.token){
                    cookie.set('token', data.token);
                    console.log(cookie.get('token'))
                    this.$router.push('game');
                }
            })
        }
    }
}
</script>