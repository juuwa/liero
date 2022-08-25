<script setup>
import { ref } from 'vue'
import Button from "@/components/Button.vue"

const gameStart = ref(false)
</script>

<template>
  <div class="flex flex-col justify-evenly gap-10">
    <div class="self-center">
      <h1 class="text-white text-5xl md:text-8xl mb-20">Matotappelu</h1>
      <div v-if="!gameStart">
        <Button @click="gameStart = true" view="">Aloita</Button>
      </div>
      <Transition>
        <div v-if="gameStart" class="flex flex-col gap-2">
          <Button view="weapons">Aseet</Button>
          <Button view="armors">Suojat</Button>
          <Button view="worms">Madot</Button>
        </div>
      </Transition>
    </div>
    <div class="self-center">
      <a class="text-white" href="https://github.com/juuwa/matotappelu">Github</a>
    </div>
  </div>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>