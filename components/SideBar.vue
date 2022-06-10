<template>
    <div id="SideBar" @mouseover="mouse_over" @mouseout="mouse_out">
        <div id="logo" :style="{'background-image': 'url('+logo+')'}"></div>
        <form id="search">
            <div>
                <input type="text" id="search_text" v-model="search_text">
                <div type="submit" id="search_send"><i class="material-icons">search</i></div>
            </div>
            <p id="search_result">{{ search_text }}</p>
        </form>
        <div id="menu">
            <button class="btn"><span class="material-icons">person</span><p>Perfil</p></button>
            <button class="btn"><span class="material-icons">settings</span><p>Configurações</p></button>
            <button class="btn"><span class="material-icons">help_outline</span><p>Ajuda</p></button>
            <button class="btn" @click="logout"><span class="material-icons">power_settings_new</span><p>Sair</p></button>
        </div>
        <p id="version">v1.00.001</p>
    </div>
</template>

<script>
export default {
    name: 'SideBar',
    emits: ['verifyLogin'],
    data () {
        return {
            logo: null,
            logo_min: require("/static/logo.png"),
            logo_max: require("/static/logo_ext.png"),
            search_text: null,
        }
    },
    props: {
    },
    methods: {
        logout () {
            sessionStorage.setItem('access','')
            sessionStorage.setItem('refresh','')
            this.$emit('verifyLogin')
        },
        mouse_over () {
            this.logo = this.logo_max
        },
        mouse_out () {
            this.logo = this.logo_min
        }
    },
    mounted () {
        this.logo = this.logo_min
        // this.search()
    },
}
</script>

<style scoped>
#SideBar {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    width: 60px;
    height: 100%;
    background-color: #222;
    transition: .3s ease-in-out;
    z-index: 1000;

    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
}
#SideBar:hover {
    width: 250px;
}

/************************************************/

#logo {
    background-position: center;
    background-size: cover;
    width: 60px;
    height: 100px;
    margin-bottom: 25px;
    transition: .3s ease-in-out;

    /* object-position: center;
    object-fit: cover; */
}
#SideBar:hover #logo  {
    transition: .3s ease-in-out;
    width: 200px;
}

/************************************************/

#search {
    position: relative;
    width: 60px !important;
    height: 100%;
    transition: .3s ease-in-out;

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
}
#SideBar:hover #search  {
    transition: .3s ease-in-out;
    width: 200px !important;
    border-radius: 8px;
}
#search_text {
    border: unset;
    padding: unset;
    width: 60px;
    height: 30px !important;
    color: #444;
    background-color: #444 !important;
    text-align: center;
    transition: .3s ease-in-out;
}
#SideBar:hover #search_text  {
    width: 200px;
    color: #cacaca;
    transition: .3s ease-in-out;
}
#search_text:focus {
    border-bottom: 1px solid #9e9e9e !important;
    box-shadow: 0 1px 0 #cacaca !important;
}
#search_send{
    position: absolute;
    top: 0;
    left: 0;
    width: 60px;
    height: 30px;
    color: #cacaca;
    background-color: rgb(0, 0, 0, 0);
    border: 0;

    display: flex;
    justify-content: center;
    align-items: center;
}
#search_result {
    color: #cacacaca;
}

/************************************************/

#SideBar .btn {
    border: unset;
    width: 60px;
    height: 30px;
    margin: 8px;
    background-color: rgb(191, 191, 191);
    transition: .3s ease-in-out;

    display: flex;
    align-items: center;
}
#SideBar .btn:hover {
    background-color: rgb(146, 146, 146);
}
#SideBar:hover .btn  {
    transition: .3s ease-in-out;
    width: 200px;
}
#SideBar .btn .material-icons {
    margin: 0 auto;
}
#SideBar:hover .btn .material-icons {
    margin-left: 12px;
    margin-right: 12px;
}
#SideBar .btn p {
    display: none;
}
#SideBar:hover .btn p {
    display: block;
}

/************************************************/

#version {
    color: #999;
    font-size: 10px;
}

/************************************************/

</style>