<template>
  <div class="blog">
    <h1>블로그</h1>

    <!-- 검색창 추가 -->
    <input type="text" v-model="searchQuery" placeholder="검색어를 입력하세요..." class="search-input" />

    <div v-for="post in filteredPosts" :key="post.id" class="post">
      <h2>{{ post.title }}</h2>
      <p v-html="post.content"></p>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import { marked } from "marked";

// Markdown 데이터 (임시 JSON)
const posts = ref([
  {
    id: 1,
    title: "Vue 3로 블로그 만들기",
    content: marked("# Vue 3 블로그 만들기\n이것은 Vue 3을 활용한 블로그 튜토리얼입니다."),
  },
  { id: 2, title: "Vue Router 기초", content: marked("**Vue Router는 페이지 이동을 담당합니다.**") },
]);

const searchQuery = ref("");

// 검색 기능 (제목 및 본문에서 검색)
const filteredPosts = computed(() => {
  return posts.value.filter(
    (post) =>
      post.title.toLowerCase().includes(searchQuery.value.toLowerCase()) ||
      post.content.toLowerCase().includes(searchQuery.value.toLowerCase())
  );
});
</script>

<style lang="scss" scoped>
@use "@/styles/main.scss";

.blog {
  padding: 2rem;
}

.search-input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  margin-bottom: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.post {
  border-bottom: 1px solid #ddd;
  padding-bottom: 20px;
  margin-bottom: 20px;
}
</style>
