<script setup lang="ts">
import type { Article } from '../types/Article';

defineProps<{
  article: Article;
  searchQuery: string;
}>();

const highlightText = (text: string, query: string): string => {
  if (!query) return text;
  const regex = new RegExp(`(${query})`, 'gi');
  return text.replace(regex, '<mark>$1</mark>');
};
</script>

<template>
  <div class="result-item">
    <h3 class="title" v-html="highlightText(article.title, searchQuery)"></h3>
    <p class="date">{{ new Date(article.date).toLocaleDateString() }}</p>
    <p class="content" v-html="highlightText(article.content, searchQuery)"></p>
  </div>
</template>

<style scoped>
.result-item {
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  background: white;
}

.title {
  margin: 0 0 0.5rem 0;
  color: #333;
}

.date {
  font-size: 0.9rem;
  color: #666;
  margin-bottom: 0.5rem;
}

.content {
  margin: 0;
  color: #444;
}

:deep(mark) {
  background-color: #fff3b4;
  padding: 0.1em 0.2em;
  border-radius: 2px;
}
</style>