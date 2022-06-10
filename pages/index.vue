<template>
  <div id="index"> 
    <NuxtLink id="button_home" to="/home">Home</NuxtLink>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  components: {
  }
}
</script>

<style>
* {
  font-family: 'Ubuntu', sans-serif;
}
#index {
  display: flex;
  justify-content: center;
  align-items: center;
}
#button_home {
  width: 100px;
  line-height: 40px;
  border: 2px solid rgb(93, 147, 201);
  background-color: rgb(93, 147, 201);
}
#button_home:hover {
  background-color: rgb(93, 147, 201, 0);
}
</style>