<script setup lang="ts">
import { ref } from "vue";
import SearchInput from "./components/SearchInput.vue";
import SearchResults from "./components/SearchResults.vue";
import { articles } from "./data/articles";

const searchQuery = ref("");

const handleSearch = (query: string) => {
  searchQuery.value = query;
};
</script>

<template>
  <div class="container">
    <h1>Search</h1>
    <div class="search-container">
      <SearchInput @search="handleSearch" />
      <SearchResults :articles="articles" :searchQuery="searchQuery" />
    </div>
  </div>
</template>

<style>
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, sans-serif;
  background-color: #f5f5f5;
  color: #333;
}

.container {
  max-width: 1200px;
  margin: 2rem auto;
  padding: 0 1rem;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 2rem;
  color: #000;
}

.search-container {
  background: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.author-info {
  margin-top: 2rem;
  padding: 1rem;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.author-info h2 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.author-info p {
  margin-bottom: 1rem;
}

.social {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.twitter-follow {
  background: #1da1f2;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
}

.followers {
  color: #666;
  font-size: 0.9rem;
}
</style>
