<template>
  <div>
    <img v-if="error.statusCode === 404" src="/error 404.png" alt="">
    <h1 v-else>An error occurred</h1>
    <NuxtLink to="/">Página Inicial</NuxtLink>
  </div>
</template>

<script>
  export default {
    props: ['error'],
    layout: 'error'
  }
</script>

<style scoped>
div {
  width: 100vw;
  height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
div img {
  width: 20%;
  margin-bottom: 32px;
}
a {
  text-decoration: unset;
  font-size: 16px;
  line-height: 30px;
  padding: 8px;
  border-radius: 8px;
  color: rgb(26, 39, 84);
  border: 3px solid rgb(112, 252, 217);
  background-color: rgb(112, 252, 217);
  transition: .2s ease-in-out;
}
a:hover {
  background-color: rgb(0,0,0,0);
  border: 3px solid rgb(112, 252, 217);
}
</style>