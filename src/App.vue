<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import CustomButton from './components/CustomButton.vue'

const mensaje = () => {
  console.log('Esto es un mensaje')
}

const mensaje2 = () => {
  console.log('Esto es otro mensaje')
}

</script>

<template>
  <CustomButton
    title="Mi botón custom"
    color="secondary"
    @click="mensaje"
  />
  <CustomButton
    title="Mi botón custom 2"
    color="yellow"
    @click="mensaje2"
  />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
