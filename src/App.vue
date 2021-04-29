<template>
  <div id="app">
    <div id="not-footer">
      <Navbar />
    </div>
    <Footer id="footer" />
  </div>
</template>

<script lang="ts">
  import { Component, Vue } from "vue-property-decorator";
  import HelloWorld from "@/components/HelloWorld.vue";
  import Navbar from "@/components/Navbar.vue";
  import Footer from "@/components/Footer.vue";

  @Component({
    components: {
      Navbar,
      Footer,
    }
  })
  export default class App extends Vue { }
</script>

<style lang="scss">
  @import "scss/_variables.scss";
  // Import Bulma and Buefy styles
  @import "~bulma";
  @import "~buefy/src/scss/buefy";

  #app {
    font-family: "Helvetica Neue", Helvetica, sans-serif;
    font-size: 16px;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }
  #not-footer {
    flex: 1 0 auto;
    min-height: 100vh;
    background-image: url("./assets/cerro-tololo.png");
    background-position: right center;
    background-size: cover;
    background-attachment: fixed;
    background-repeat: no-repeat;
  }
  #footer {
    flex-shrink: 0;
  }
</style>
