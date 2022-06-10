<template>
    <div id="Action">
        <a href="#NovoTicket"><b>+</b> Ticket</a>
        <a class='disabled'><b>+</b> Empresa</a>
        <a class='disabled'><b>+</b> Cliente</a>
        <a v-if="list_grid" @click="list_grid=false"><b>List</b>/Grid</a>
        <a v-else @click="list_grid=true">List/<b>Grid</b></a>
    </div>
</template>

<script>
export default {
    name: 'Action',
    data () {
        return {
            list_grid: true,
        }
    }
}
</script>

<style scoped>
#Action {
    background-color: rgb(216,216,216);
    border-radius: 5px;
    margin: 16px 16px 16px 0;

    display: flex;
    justify-content: space-evenly;
    align-items: center;
}
#Action a {
    background-color: rgb(191, 191, 191);
    width: 100px;
    color: #444;
    line-height: 30px;
    text-align: center;
    border: unset;
    text-decoration: unset;
}
#Action a:hover {
    background-color: rgb(146, 146, 146);
}
.disabled {
  background: rgb(100,100,100) !important;
}
.disabled:hover {
  background: rgb(100,100,100) !important;
}
</style>