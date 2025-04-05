<script setup lang="ts">
import { defineProps, computed } from "vue"
import Icon from "../Icon/Icon.vue";

type RateProps = {
  max: number;
  icon: string;
  readonly: boolean;
  voidIcon: string;
}

const props = defineProps<RateProps>()

function getRateStatus(score: number, index: number) {
  if (score > index) {
    return { status: 'full', score: 1 }
  }
  return { status: 'empty', score: 0}
}

const list = computed(() => {
  return getRateStatus(props.max, props.icon)
})

const onClickItem = (index: number) => {}

const updateRanges = () => {}

const getScoreByMouse = () => {}
</script>

<template>
  <div class="rate">
    <div v-for="(item, index) in list">
      <Icon :name="item.score > index ? icon : voidIcon" />
    </div>
  </div>
</template>