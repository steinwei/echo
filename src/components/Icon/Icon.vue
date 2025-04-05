<template>
  <img :src="name" />
</template>

<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps({
  name: {
    type: String,
    required: true,
  }
})
</script>

<style lang="scss" scoped></style>