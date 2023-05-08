<script setup>
defineProps({
  show: Boolean,
  title: String,
});
</script>

<template>
  <div v-if="show" class="modal-container flex column">
    <h4>{{ title }}</h4>
    <slot></slot>
  </div>
</template>

<style scoped>
.modal-container {
  background: #ffffff;
  border-radius: 12px;
  padding: 2.4rem 3.2rem;
}

h4 {
  font-style: normal;
  font-weight: 500;
  font-size: 2.4rem;
  color: #333333;
}
</style>
