<script setup>
defineProps(['adicinar'])



</script>



<template>
    <div class="resultado">
        <div v-for="usuario in adicinar" class="resultado">
        <div>Nome: <p>{{ usuario.nome }}</p></div>
        <div>Email: <p>{{ usuario.email }}</p></div>
      </div>
            
      </div>

                

</template>

<style scoped>
.resultado{
    color: rgb(255, 255, 255);
    background-color: blue;
    border-radius: 6px;
    height: 450px;
    width: 450px;
    margin-left: 5px;
}
</style>