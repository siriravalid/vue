<template>
  <div>
    <h1 class="cosmetic-name">{{ cosmeticName }}</h1>
    <h2 class="author-name">{{ authorName }}</h2>
  </div>
</template>

<script>
export default {
  name: 'MyHeader',
  props: {
    cosmeticName: String,
    authorName: String
  }
};
</script>

<style scoped>
div {
  text-align: center;
}

.cosmetic-name {
  color: coral;
  font-size: 40px; 
}

.author-name {
  color: black;
  font-size: 20px; 
}
</style>
