<template>
  <v-app>
    <v-main>
      <Navbar />
      <!-- <HelloWorld /> -->
      <MainContent />
      <v-footer class="d-flex align-center justify-center flex-column" color="#22333b">
        <div class="white--text">&copy; {{ new Date().getFullYear() }}</div>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script>
/* import HelloWorld from "./components/HelloWorld"; */
import Navbar from "./components/Navbar.vue";
import MainContent from "./components/MainContent.vue";

export default {
  name: "App",

  components: {
    /* HelloWorld, */
    Navbar,
    MainContent,
  },
};
</script>
