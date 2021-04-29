<template>
  <footer class="footer">
    <!-- <div class="content has-text-centered">
      <p>
        The
        <strong>Skynet site</strong> by
        <a href="https://finnjames.dev">Finn James</a>. The source code is licensed under the
        <a
          href="https://opensource.org/licenses/GPL-3.0"
        >GPLv3</a>. The website content is licensed
        under
        <a
          href="http://creativecommons.org/licenses/by-nc-sa/4.0/"
        >CC BY-NC-SA 4.0</a>.
      </p>
    </div>-->
    <div class="columns">
      <div class="column">
        <strong>Skynet</strong>
        <p>The Skynet Robotic Telescope Network operates out of the University of North Carolina at Chapel Hill.</p>
        <p>Supported by the National Science Foundation, North Carolina Space Grant, and the Mount Cuba Astronomical Foundation</p>
      </div>
      <div class="column">
        <strong>Latest</strong>
      </div>
      <div class="column">
        <strong>Contact Us</strong>
        <p>
          Skynet Robotic Telescope Network
          University of North Carolina
          269 Phillips Hall, CB #3255
          Chapel Hill, NC 27599
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
  import { Component, Prop, Vue } from "vue-property-decorator";

  @Component
  export default class Footer extends Vue {}
</script>

<style lang="scss" scoped>
  @import "@/scss/_variables.scss";
</style>