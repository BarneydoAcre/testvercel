<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <SideBar @verifyLogin="verifyLogin"/>
    <Ticket />
  </div>
</template>

<script>
import SideBar from '/components/SideBar.vue'
import Ticket from '/components/Ticket.vue'

export default {
    name: 'Home',
    components: {
        SideBar,
        Ticket,
    },
    methods: {
        async verifyLogin () {
            let data = {
                // "access": sessionStorage.getItem("access"),
                "token": sessionStorage.getItem("access")
            }
            const req = await fetch('http://127.0.0.1:8000/jwt/verify/', {
                method: 'POST',
                body: JSON.stringify(data),
                headers: {"Content-type": "application/json"}
            })
            const res = await req.json()
            if (req.status == '200') {
                sessionStorage.setItem('keys', {'access': res.access, 'verify': res.verify})
            }else{
                window.location.href = "http://localhost:3000/login"
                this.info = 'login inválido ou expirado'
            }
        }
    },
    created () {
        this.verifyLogin()
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap');
* {
  padding: 0;
  margin: 0; 
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
  font-size: 12px;
}
.home {
  width: 100%;
  height: 100%;
  display: grid; 
  grid-template-columns: 60px calc(100vw - 60px);
  grid-template-rows: 100vh;
  grid-template-areas: 
  "sidebar ticket"; 
}
#SideBar {
  grid-area: sidebar;
}
#Ticket {
  grid-area: ticket;
}

a .disabled {
  background: rgb(78, 78, 78) !important;
}
a .disabled:hover {
  background: rgb(77, 77, 77) !important;
}
input {
    border: unset;
    border-bottom: 1px solid #999;
    width: 140px;
    height: 30px;
    background: rgb(255, 255, 255,0)
}
input:focus-visible {
  outline: unset;
}
textarea {
  border: 1px solid #999;
  max-height: 100px;
  min-height: 100px;
  max-width: 100%;
  min-width: 100%;
}
textarea:focus-visible {
  outline: unset;
}
textarea:active,
textarea:hover {
  border: 1px solid #999;
}
h6 {
    margin: unset;
    padding: unset;
    font-size: 10px;
    color: #9e9e9e;
    transform: translateY(4px);
}
</style>