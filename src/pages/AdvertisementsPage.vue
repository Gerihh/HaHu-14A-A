<template>
  <q-page>
    <div class="card-container">
      <CardComponent v-for="ad in advertisements" :key="ad" />
    </div>
  </q-page>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
import axios from "axios";
import CardComponent from "src/components/CardComponent.vue";

const advertisements = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get("http://localhost:3000/advertisements");
    advertisements.value = response.data;
  } catch (error) {
    console.error("Error fetching advertisements:", error);
  }
});
</script>

<style scoped>
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

/* Adjust the width to make the cards smaller and fit 3 in a row */
.card-container .card-component {
  width: calc(33.33% - 10px);
  margin-bottom: 20px; /* Add some margin between cards */
}
</style>
