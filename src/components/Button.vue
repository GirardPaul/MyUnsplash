<script setup>
import { ref } from "vue";
const props = defineProps({
  type: {
    type: String,
    default: "success",
    validator: (value) => {
      return ["success", "danger", "outline-danger", "outline"].includes(value);
    },
  },
  size: {
    type: String,
    default: "lg",
    validator: (value) => {
      return ["sm", "md", "lg"].includes(value);
    },
  },
});
</script>

<template>
  <button type="button" :class="['btn', `btn-${type}`, `btn-${size}`, 'pointer']">
    <slot></slot>
  </button>
</template>

<style scoped>
.btn {
  box-shadow: 0px 1px 6px rgba(0, 0, 0, 0.1);
  border-radius: 12px;
  font-size: 1.6rem;
  color: #fff;
  font-style: normal;
  font-weight: 700;
  border: none;
  outline: none;
}
.btn-success {
  background-color: #3db46d;
}
.btn-danger {
  background-color: #eb5757;
}
.btn-outline-danger {
  background-color: transparent !important;
  border: 1px solid #eb5757 !important;
  color: #eb5757 !important;
  font-size: 1rem !important;
}

.btn-outline {
  background-color: transparent !important;
  color: #bdbdbd !important;
}

.btn-outline:hover {
  background-color: #bdbdbd !important;
  color: #fff !important;
}

.btn-lg {
  padding: 1.8rem 2.6rem;
}
.btn-md {
  padding: 1.5rem 2.1rem;
}
.btn-sm {
  padding: 0.5rem 1.5rem;
}
</style>
