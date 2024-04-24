<template>
    <div id="container-agregar-nombre">
        <h1>NOMBRE: {{ nombre}} Apellido {{ apellido }} </h1>
        
    </div>
       
    
</template>

<script>

export default {
    name:'AgregarNombre',
    props:{
    
        nombre: String,
        apellido: String
        
    },
    methods: {
        
    },
}
</script>

<style>

#npt{
    margin-right: 3%;
}

</style>