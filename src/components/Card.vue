<script setup>
import { ref } from "vue";
import Button from "./Button.vue";
defineProps({
  document: Object,
});

const deleteDocument = (id) => {
  console.log(id);
};
</script>

<template>
  <div class="card pointer" :style="`background-image: url('${document.url}')`">
    <Button
      class="btn d-none"
      type="outline-danger"
      size="sm"
      @click="deleteDocument(document.id)"
      >Delete</Button
    >
    <h3 class="d-none">{{ document.label }}</h3>
  </div>
</template>

<style scoped>
.d-none {
  display: none;
}
.btn {
  align-self: flex-end;
}

h3 {
  font-style: normal;
  font-weight: 700;
  font-size: 1.8rem;
  color: #ffffff;
}

.card {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  border-radius: 16px;
  box-shadow: 0px 1px 6px rgba(0, 0, 0, 0.1);
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  padding: 1.8rem 1.8rem 3.2rem 2.4rem;
}

.card:hover * {
  display: block !important;
}
</style>
