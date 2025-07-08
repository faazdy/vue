<script setup> /*SETUP sirve para saltarnos la parte de 'export default...' */
  import HelloWorld from './components/HelloWorld.vue'
  import CardwithImage from './projects/CardwithLikes.vue'

</script>

<template>
  <HelloWorld username="diego" userPic="https://static.vecteezy.com/system/resources/thumbnails/041/880/991/small_2x/ai-generated-pic-artistic-depiction-of-sunflowers-under-a-vast-cloudy-sky-photo.jpg" :likesCount="5" /> // Para pasar datos NO STRING usamos ':'
  <HelloWorld username="diego" userPic="https://static.vecteezy.com/system/resources/thumbnails/041/880/991/small_2x/ai-generated-pic-artistic-depiction-of-sunflowers-under-a-vast-cloudy-sky-photo.jpg" :likesCount="3" /> // Para pasar datos NO STRING usamos ':'
</template>

<style scoped> /*SCPED sirve para mantener los estilos nomas para el componente actual*/ 
  *{
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
  body{
    display: flex;
  }
</style>
