<template>
    <div id="container-msg">
        <h1>Mostrar Lista {{ Lista }} </h1>
    </div>
</template>

<script>
export default {
props:{
    lista: String[''],
}
}
</script>

<style>
#container-msg{
    background: rgb(116, 98, 98);
    color: rgb(208, 218, 224);    
}

</style>