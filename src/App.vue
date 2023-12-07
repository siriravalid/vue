<template>
  <div>
    <MyHeader cosmeticName="Cosmetic Information details" authorName="Sai Siri Ravali" />
    <CosmeticBox :cosmetics="cosmetics" />
  </div>
</template>

<script>
import MyHeader from '@/components/MyHeader.vue';
import CosmeticBox from '@/components/CosmeticBox.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    CosmeticBox
  },
  data() {
    return {
      cosmetics: []
    };
  },
  methods: {
    async fetchCosmetics() {
      try {
        const res = await fetch('https://siriravali.onrender.com/api');
        if (!res.ok) {
          throw new Error(`Failed to fetch: ${res.statusText}`);
        }
        const data = await res.json();
        return data;
      } catch (error) {
        console.error('Error fetching cosmetics:', error);
        return [];
      }
    }
  },
  async created() {
    this.cosmetics = await this.fetchCosmetics();
  }
};
</script>

<style>
/* Add global styles if needed */
</style>
