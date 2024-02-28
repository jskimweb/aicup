<template>
  <div class="home" @click="router.push('/category')">
    <img src="../assets/image/logo.png" class="logo" alt="logo" />
    <transition name="fade">
      <span v-if="clickable" class="text">화면 아무 곳이나 클릭해주세요</span>
    </transition>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router';

const router = useRouter();

const clickable = ref(false);

onMounted(() => {
  setTimeout(() => (clickable.value = true), 1000);
});
</script>

<style scoped lang="scss">
.home {
  height: 100vh;
  cursor: pointer;
  .logo {
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 70vw;
  }
  .text {
    position: fixed;
    left: 50%;
    top: 80%;
    transform: translate(-50%, -50%);
    white-space: nowrap;
    opacity: 0.6;
  }
}

.fade-enter-active {
  transition: opacity 1s;
}
.fade-enter-from {
  opacity: 0;
}
</style>
