<template>
  <div>
    <div v-for="cosmetic in cosmetics" :key="cosmetic.id">
      <SingleCosmetic :cosmetic="cosmetic" />
    </div>
  </div>
</template>

<script>
import SingleCosmetic from './SingleCosmetic.vue';

export default {
  name: 'CosmeticBox',
  props: {
    cosmetics: Array
  },
  components: {
    SingleCosmetic
  }
};
</script>

<style scoped>
div {
  text-align: center;
}
</style>
