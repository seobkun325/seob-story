<template>
  <div class="layout">
    <Header />

    <div class="container">
      <Sidebar />
      <main class="content">
        <slot />
      </main>
    </div>

    <Footer />
  </div>
</template>

<script setup>
import Header from "@/components/Header.vue";
import Sidebar from "@/components/Sidebar.vue";
import Footer from "@/components/Footer.vue";
</script>

<style lang="scss" scoped>
@use "@/styles/main.scss";

.layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.container {
  display: flex;
  flex: 1;
}

.content {
  flex: 1;
  padding: 2rem;
}
</style>
