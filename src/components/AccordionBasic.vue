<script setup lang="ts">
import { computed, onMounted, onUnmounted, ref } from "vue"
import { XMarkIcon } from "@heroicons/vue/20/solid"

const contents = ref<HTMLElement>()

const show = ref(false)
const toggle = () => (show.value = !show.value)

const targetHeight = ref(0)
const height = computed(() => (show.value ? targetHeight.value : 0))

const setTargetHeight = () => (targetHeight.value = (contents.value! as HTMLElement).offsetHeight)

onMounted(() => {
  setTargetHeight()

  window.addEventListener("resize", setTargetHeight)
})

onUnmounted(() => {
  window.removeEventListener("resize", setTargetHeight)
})
</script>

<template>
  <div
    class="group rounded-xl border border-[#333333] bg-[#222] transition duration-500 hover:bg-[#292929] md:rounded-2xl">
    <div @click="toggle" class="flex cursor-pointer items-center p-5 md:p-6">
      <div class="text-base text-[#F1F0EE] transition group-hover:text-white md:text-lg">
        <slot name="title" />
      </div>

      <div class="relative ml-auto">
        <XMarkIcon
          :class="{ 'rotate-180': show, 'rotate-45': !show }"
          class="h-5 w-5 text-[#D7D5D1] transition-transform duration-500 md:h-6 md:w-6" />
      </div>
    </div>

    <div
      :style="{
        height: `${height}px`,
      }"
      class="overflow-hidden px-5 transition-[height] duration-500 will-change-[height] md:px-6">
      <div ref="contents" class="space-y-4 pb-5 font-light leading-relaxed tracking-wide text-[#B1AFAD] md:pb-6">
        <slot />
      </div>
    </div>
  </div>
</template>
