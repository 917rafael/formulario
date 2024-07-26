<!-- eslint-disable vue/multi-word-component-names -->

<script setup>

const props = defineProps({
  usuarios: Array
});
</script>

<template>
  <div>
    <h2>Resultado</h2>
    <ul>
      <li v-for="(usuario, index) in props.usuarios" :key="index">
        {{ usuario }} 
      </li>
    </ul>
  </div>
</template>

<style scoped>

</style>