<script setup>
import { ref } from 'vue';

const props = defineProps({
  title: String,
  price: Number,
  description: String,
  image: String
})

const isFavorite = ref(false);

const handleFavorite = ()=>{
  isFavorite.value = !isFavorite.value;
}
</script>
<template>
    <article class="card">
      <img :src="props.image" :alt="props.title +' pic'">
      <h2>{{ props.title }}</h2>
      <strong>${{ props.price }}</strong>
      <p>{{ props.description }}</p>
      <hr>
      <button :class="isFavorite ? 'favorite' : ''" @click="handleFavorite">{{ isFavorite ? '❤️ Favorite' : '🖤 Make Favorite' }}</button>
    </article>
</template>

<style scoped>
  .card {
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 16px;
    text-align: center;
  }
  .card img {
    width: 100%;
    height: auto;
    border-radius: 8px;
  }
  .card button {
    background-color: #e7e7e7;
    color: rgba(0, 0, 0, 0.774);
    border: none;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
    transition: .3s ease ;
  }
  button.favorite {
    background-color: #ff00559f;
    box-shadow: 0px 5px 10px -5px #ff00559f;
    color: white;
  }
  button:hover {
    transform: translateY(-2px);
  }
</style>