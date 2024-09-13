<template>
  <div class="flex" :style="`width:${data.length * 20}vw`">
    <div
      v-for="(item, index) in Props.data"
      :key="item.name"
      class="flex flex-col items-center w-[20vw]"
    >
      <div class="relative">
        <img :src="item.img" class="filter w-[9vw]" />
      </div>
      <span class="text-[2.99vw] text-[#676c6c]">
        {{ item.name }}
      </span>
    </div>
  </div>
</template>
<script setup>
import { defineProps, defineEmits } from 'vue'
const Props = defineProps({
  data: {
    type: Array,
    required: true
  }
})
const emit = defineEmits(['click'])
</script>
<style scoped>
.filter {
  filter: url("data:image/svg+xml;utf8,<svg xmlns='http://ww.w3.org/2000/svg'><filter id='colorize'><fecolorMatrix type='matrix' values='1 0 0 0 0.698 0 0 0 0 0 0 0 0 0 0 0 0 0 1 0' /></filter></svg>#colorize");
}
</style>
