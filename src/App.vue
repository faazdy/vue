<script setup> /*SETUP sirve para saltarnos la parte de 'export default...' */
  import HelloWorld from './components/HelloWorld.vue'
  import CardwithImage from './projects/CardwithLikes.vue'

</script>

<template>
  <!--<CardwithImage username="Londra" :likesCount="5" /> -->
  <HelloWorld />
</template>

<style scoped> /*SCPED sirve para mantener los estilos nomas para el componente actual*/ 
  *{
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
  body{
    display: flex;
  }
</style>
