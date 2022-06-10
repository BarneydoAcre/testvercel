<template>
    <section id="">
        <div id="login">
            <div id="logo">
                <img src="/logo_ext.png" alt="">
            </div>
            <div id="response">{{ info }}</div>
            <form id="inputs">
                <input type="text" id="username" class="input" placeholder="username">
                <input type="password" id="password" class="input" placeholder="password">
                <button type="submit" id="submit" class="input-btn" @click="loginValidate($event)">Enviar</button>
            </form>
        </div>
    </section>
</template>

<script>
export default {
    name: "login",
    data () {
        return {
            info: '',
        }
    },
    methods: {
        async loginValidate (e) {
            e.preventDefault()
            let data = {
                "username": self.username.value,
                "password": self.password.value
            }
            const req = await fetch('http://127.0.0.1:8000/jwt/create/', {
                method: 'POST',
                body: JSON.stringify(data),
                headers: {"Content-type": "application/json"}
            })
            const res = await req.json()

            if (req.status == '200') {
                sessionStorage.setItem('access', res.access)
                sessionStorage.setItem('refresh', res.refresh)
                window.location.href = "http://localhost:3000/dashboard/"
            }else{
                this.info = 'login inválido'
            }
        }
    }
}
</script>

<style>
* {
    padding: 0;
    margin: 0; 
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
    font-size: 12px;
}
section {
    width: 100vw;
    height: 100vh;

    display: flex;
    align-items: center;
    justify-content: center;
}
#login {
    display: flex;
    align-content: center;
    justify-content: center;
    flex-direction: column;
}
#inputs {
    display: flex;
    align-content: center;
    justify-content: center;
    flex-direction: column;
}
.input {
    width: 90%;
    margin: 1vh auto;
    border: 1.5px solid rgb(5, 1, 29);
    border-radius: 1vh;
    padding: 0.5em;
}
.input-btn {
    width: 90%;
    margin: 1vh auto;
    color: white;
    background-color: rgb(66, 66, 224);
    border: unset;
    border-radius: 1vh;
    box-shadow: 0 1px 5px 0 black;
    padding: 0.5em;
}
</style>