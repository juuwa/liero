<script setup>
defineProps({
  view: String
})

const changeView = (view) => {
  return navigateTo(`/${view}`)
}

</script>

<template>
  <div class="flex justify-center select-none">
    <div class="rounded-lg p-2 cursor-pointer bg-slate-400 text-center w-40 border-2 hover:bg-slate-600"
      @click="changeView($props.view)">
      <span class="text-white text-2xl">
        <slot></slot>
      </span>
    </div>
  </div>
</template>