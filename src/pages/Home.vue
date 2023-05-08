<script setup>
import { ref } from "vue";
import Button from "../components/Button.vue";
import InputText from "../components/InputText.vue";
import Modals from "../components/Modals.vue";
const showCreateModal = ref(false),
  showDeleteModal = ref(false),
  searchContent = ref("");

const openCreateModal = () => {
  showCreateModal.value = true;
  console.log(searchContent.value);
};
const openDeleteModal = () => {
  showDeleteModal.value = true;
};
</script>

<template>
  <Modals
    class="modal-create"
    :show="showCreateModal"
    title="Add a new photo"
  ></Modals>
  <header>
    <div class="flex justify-between align-center header-content">
      <div class="flex align-center flex-grow logo-search-content">
        <img src="src/assets/my_unsplash_logo.svg" alt="My Unsplash logo" />
        <InputText
          class="ml-4 input-search"
          icon="search"
          placeholder="Search by name"
          v-model="searchContent"
        />
      </div>
      <Button class="btn" type="success" @click="openCreateModal()"
        >Add a photo</Button
      >
    </div>
  </header>
</template>

<style scoped>
header {
  padding: 3.2rem 10rem 7.5rem 10rem;
}
.ml-4 {
  margin-left: 4rem;
}
.input-search {
  width: 30rem;
}

.modal-create {
  width: 62rem;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@media screen and (max-width: 1200px) {
  header {
    padding: 3.2rem 7rem 7.5rem 7rem;
  }
}
@media screen and (max-width: 900px) {
  header {
    padding: 3.2rem 5rem 7.5rem 5rem;
  }
}

@media screen and (max-width: 768px) {
  .header-content > div:first-child {
    width: 100%;
  }
  .input-search {
    width: 100%;
  }

  .header-content {
    flex-direction: column;
    align-items: flex-start;
  }

  .btn {
    margin-top: 2rem;
    width: 100%;
  }
}
@media screen and (max-width: 576px) {
  .logo-search-content {
    flex-direction: column;
    align-items: flex-start;
  }
  .input-search {
    margin-left: 0;
    margin-top: 2rem;
  }
}

@media screen and (max-width: 400px) {
  header {
    padding: 3.2rem 1.5rem 7.5rem 1.5rem;
  }
}
</style>
