<script setup>
defineProps({
  icon: String,
  placeholder: String,
  label: String,
  modelValue: String,
});

const emit = defineEmits(["update:modelValue"]);
</script>

<template>
  <div class="form-group">
    <p v-if="label">{{ label }}</p>
    <div class="input-container">
      <span v-if="icon" class="material-icons">{{ icon }}</span>
      <input
        :class="{
          'input-with-icon': icon,
          'input-with-label': label,
        }"
        type="text"
        :value="modelValue"
        :placeholder="placeholder"
        @input="emit('update:modelValue', $event.target.value)"
      />
    </div>
  </div>
</template>

<style scoped>
p {
  font-style: normal;
  font-weight: 500;
  font-size: 1.4rem;
  color: #4f4f4f;
}
input {
  border: none;
  outline: none;
  font-size: 1.4rem;
  width: 100%;
  background: transparent;
  color: #bdbdbd;
}

span {
  font-size: 2rem;
  color: #bdbdbd;
}

.input-with-label {
  margin-top: 1rem;
}

.input-with-icon {
  margin-left: 2rem;
}

.input-container {
  padding: 1.9rem;
  display: flex;
  align-items: center;
  background-color: transparent;
  border: 1px solid #bdbdbd;
  filter: drop-shadow(0px 1px 6px rgba(0, 0, 0, 0.1));
  border-radius: 12px;
  width: 100%;
}

.input-container:has(input:focus) {
  border: 1px solid #4f4f4f;
  filter: drop-shadow(0px 1px 6px rgba(0, 0, 0, 0.1));
}
</style>
