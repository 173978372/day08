<template>
  <div>{{ props.data.name }}</div>
  <div class="flex">
    <img v-for="item in props.data.children" :key="item.id" :src="item.imageUrl" alt="" />
  </div>
</template>
<script setup>
import { defineProps } from 'vue'
const props = defineProps({
  data: {},
  required: true
})
</script>
