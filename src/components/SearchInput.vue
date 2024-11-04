<script setup lang="ts">
import { ref } from "vue";

const searchQuery = ref("");

const emit = defineEmits<{
  (e: "search", query: string): void;
}>();

const handleInput = () => {
  emit("search", searchQuery.value);
};
</script>

<template>
  <div class="search-input">
    <input
      v-model="searchQuery"
      @input="handleInput"
      type="text"
      placeholder="Search articles..."
      class="search-field"
    />
  </div>
</template>

<style scoped>
.search-input {
  margin-bottom: 2rem;
}

.search-field {
  width: 100%;
  padding: 1rem;
  font-size: 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  transition: border-color 0.3s;
}

.search-field:focus {
  outline: none;
  border-color: #1da1f2;
}
</style>
