<script setup lang="ts">
import { computed } from "vue";
import type { Article } from "../types/Article";
import SearchResultItem from "./SearchResultItem.vue";

const props = defineProps<{
  articles: Article[];
  searchQuery: string;
}>();

const filteredArticles = computed(() => {
  if (!props.searchQuery) return props.articles;

  const query = props.searchQuery.toLowerCase();

  return props.articles.filter(
    (article) =>
      article.title.toLowerCase().includes(query) ||
      article.content.toLowerCase().includes(query)
  );
});
</script>

<template>
  <div class="search-results">
    <p class="results-count">{{ filteredArticles.length }} posts were found.</p>
    <div class="results-list">
      <SearchResultItem
        v-for="article in filteredArticles"
        :key="article.id"
        :article="article"
        :searchQuery="searchQuery"
      />
    </div>
  </div>
</template>

<style scoped>
.search-results {
  width: 100%;
}

.results-count {
  color: #666;
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
}

.results-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}
</style>
