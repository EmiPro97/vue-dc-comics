<template>
  <div id="app">
    <!-- HEADER -->
    <Header />


    <!-- MAIN -->
    <main>Main content</main>

    <!-- FOOTER -->
    <footer>Footer here</footer>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style>
/* GENERAL STYLES */
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
