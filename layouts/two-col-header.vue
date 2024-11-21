<script setup lang="ts">
const props = defineProps({
  columnClass: {
    type: String,
  },
});
</script>

<template>
  <div class="slidev-layout two-col-header w-full h-full">
    <div class="col-header">
      <slot />
    </div>
    <div class="col-left" :class="columnClass">
      <slot name="left" />
    </div>
    <div class="col-right" :class="columnClass">
      <slot name="right" />
    </div>
  </div>
</template>

<style scoped>
.two-col-header {
  display: grid;
  gap: 20px;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  grid-template-rows: 50px auto;
}

.col-header {
  grid-area: 1 / 1 / 1 / 2;
}
.col-left {
  grid-area: 2 / 1 / 2 / 1;
}
.col-right {
  grid-area: 2 / 2 / 2 / 2;
}
</style>
