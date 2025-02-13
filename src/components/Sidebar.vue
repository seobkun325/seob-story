<template>
  <aside class="sidebar">
    <nav>
      <ul>
        <li><router-link to="/">🏠 홈</router-link></li>
        <li><router-link to="/blog">📝 블로그</router-link></li>
        <li><router-link to="/about">📌 소개</router-link></li>
      </ul>
    </nav>
  </aside>
</template>

<style lang="scss" scoped>
@use "@/styles/main.scss";

.sidebar {
  width: 250px;
  background: $secondary-color;
  padding: 1rem;

  ul {
    list-style: none;
    padding: 0;

    li {
      margin: 10px 0;
      a {
        color: white;
        font-weight: bold;
      }
    }
  }
}
</style>
