<template>
  <div class="category">
    <button @click="onClickCategory('boy')">남돌</button>
    <button @click="onClickCategory('girl')">여돌</button>
  </div>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';

const router = useRouter();

function onClickCategory(category: string) {
  router.push({ name: 'WorldCup', query: { category } });
}
</script>
