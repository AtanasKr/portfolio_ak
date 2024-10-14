<template>
  <NavBar />
  <router-view />
  <FooterBar />
</template>

<script>
import NavBar from './components/NavBar.vue';
import FooterBar from './components/FooterBar.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    FooterBar,
  }
}
</script>

<style></style>
