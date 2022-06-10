<template>
    <div id="Data">
        {{ $route.params.empresa }}
    </div>
</template>

<script>
export default {
    name: 'Data',
}
</script>

<style>
#Data {
    background-color: rgb(216, 216, 216);
    border-radius: 5px;
}

</style>