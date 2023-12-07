<template>
  <div class="cosmetic-container" :class="cosmetic.in_stock ? 'green' : 'red'">
    <div class="cosmetic-info">
      <h2>Product Name: {{ cosmetic.product_name }}</h2>
      <img :src="getShadeImage(cosmetic.shade)" alt="Cosmetic Image" class="cosmetic-image" />
      <h2>Company: {{ cosmetic.company }}</h2>
      <h2>
        Shade: 
        <span :style="{ color: getShadeTextColor(cosmetic.shade) }">{{ cosmetic.shade }}</span>
      </h2>
      <h2>Manufacturing date: {{ cosmetic.product_info.mfg_date }}</h2>
      <h2>Is Waterproof: {{ cosmetic.product_info.is_waterproof }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SingleCosmetic',
  props: {
    cosmetic: Object
  },
  methods: {
    getShadeImage(shade) {
      switch (shade.toLowerCase()) {
        case 'red':
          return 'https://images.unsplash.com/photo-1625093742435-6fa192b6fb10?w=500&h=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8bGlwc3RpY2t8ZW58MHx8MHx8fDA%3D';
        case 'purple':
          return 'https://images.unsplash.com/photo-1631214540553-ff044a3ff1d4?w=500&h=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8bWFzY2FyYXxlbnwwfHwwfHx8MA%3D%3D';
        case 'brown':
          return 'https://images.unsplash.com/photo-1531646317777-0619c7c5d1d3?w=500&h=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjN8fGZvdW5kYXRpb258ZW58MHx8MHx8fDA%3D';
        case 'darkblue':
          return 'https://images.unsplash.com/photo-1487412912498-0447578fcca8?w=500&h=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8ZXllJTIwc2hhZG93fGVufDB8fDB8fHww';
        case 'maroon':
          return 'https://images.unsplash.com/photo-1625093525885-282384697917?w=500&h=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NHx8Ymx1c2h8ZW58MHx8MHx8fDA%3D';
        case 'dark magenta':
          return 'https://images.unsplash.com/photo-1625094640367-05f84293fe42?w=500&h=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTN8fGJyb256ZXIlMjBtYWtldXB8ZW58MHx8MHx8fDA%3D';
        default:
          return 'https://example.com/default_image.jpg';
      }
    },
    getShadeTextColor(shade) {
      switch (shade.toLowerCase()) {
        case 'red':
          return 'red';
        case 'purple':
          return 'purple';
        case 'brown':
          return 'brown';
        case 'darkblue':
          return 'darkblue';
        case 'maroon':
          return 'maroon';
        case 'dark magenta':
          return 'darkmagenta';
        default:
          return 'darkmagenta';
      }
    }
  }
};
</script>

<style scoped>
h2 {
  font-size: 2em;
  margin: 0;
}

.cosmetic-container {
  color: black;
  padding: 2em;
  text-align: center;
  margin: 1.2em;
  border: 4px solid coral;
  border-radius: 8px;
}

.cosmetic-info {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.cosmetic-image {
  max-width: 10%;
  max-height: 10%; /* Ensure consistent image size */
  margin-top: 10px;
}

.green {
  background-color: lightgrey;
}

.red {
  background-color: lightyellow;
}
</style>
