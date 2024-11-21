<script setup lang="ts">
const props = defineProps({
  columnClass: {
    type: String,
  },
});
</script>

<template>
  <div class="slidev-layout two-col w-full h-full">
    <div class="col-left" :class="columnClass">
      <slot />
    </div>
    <div class="col-right" :class="columnClass">
      <slot name="right" />
    </div>
  </div>
</template>

<style scoped>
.two-col {
  display: grid;
  gap: 20px;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  align-items: center;
}

.col-left {
  grid-area: 1 / 1 / 2 / 1;
}
.col-right {
  grid-area: 1 / 2 / 2 / 2;
}
</style>
