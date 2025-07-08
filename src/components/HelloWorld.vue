<script setup>
  import { ref } from 'vue';

  const props = defineProps({
    username: String,
    userPic: String,
    likesCount: {
      type: Number,
      default: 0
    }
  })

  const likes = ref(props.likesCount);
  const maxLikes = 15;

  const likePost = () =>{
    if(likes.value < maxLikes){
      likes.value++
    } else {
      console.log('MAX LIKES REACHED');
    }
  }

  const restartLikes =() =>{
    likes.value = 0;
  }
</script>

<template>
  <div class="user-card">
    <div class="profile">
      <img :src="props.userPic" alt="userpic">
      <h2>{{ props.username }}</h2>
      <p>Software Engineer</p>
    </div>

    <div class="user-post">
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Veritatis dolorum consequatur fugit harum aliquid quia necessitatibus qui! Illum tempora at laboriosam, eos aliquam, molestiae debitis dolorum soluta ratione modi quidem.
      </p>
    </div>
    <button @click="likePost" :disabled="likes >= maxLikes">Likes: {{ likes }}</button>
    <button @click="restartLikes">RESET LIKES</button>
  </div>
</template>


<style scoped>
  *{
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
  body{
    display: flex;
  }
  .user-card {
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 16px;
    margin: 16px auto;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }

  .profile {
    text-align: center;
    margin-bottom: 16px;
  }

  .profile img {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    object-fit: cover;
  }

  .user-post {
    margin-bottom: 16px;
    font-size: 14px;
    color: #555;
  }

  button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    margin: 0 2px;
  }

  button[disabled] {
    background-color: #ccc;
    cursor: not-allowed;
  }
</style>
