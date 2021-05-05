<template>
  <div id="app">
    <!-- HEADER -->
    <Header />

    <!-- MAIN -->
    <Main />

    <!-- FOOTER -->
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  }
}
</script>

<style>
/* GENERAL STYLES */
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira Sans Condensed', sans-serif;
}

body{
    color: #fff;
    padding-top: 120px;
}

/* Layout */
.container{
  max-width: 1300px;
  height: 100%;
  margin: 0 auto;
}

.flex{
  display: flex;
}

.space-between{
  justify-content: space-between;
}

.a-items-center{
  align-items: center;
}

/* List */
ul li{
  list-style: none;
}

/* Text */
a{
  text-decoration: none;
  color: inherit;
}

.text-uppercase{
  text-transform: uppercase;
}
</style>
