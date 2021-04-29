<template>
  <b-navbar fixed-top="true">
    <template slot="brand">
      <b-navbar-item>
        <img src="@/assets/logo.png" />
        <span id="skynet">Skynet</span>
      </b-navbar-item>
    </template>
    <template slot="start">
      <b-navbar-item href="#">Home</b-navbar-item>
      <b-navbar-item href="#">My Observatory</b-navbar-item>
      <b-navbar-item href="#">Skynet Live</b-navbar-item>
      <b-navbar-dropdown label="Telescope Sites" v-bind:hoverable="true">
        <b-navbar-item href="#">Morehead</b-navbar-item>
        <b-navbar-item href="#">Cerro Tololo</b-navbar-item>
      </b-navbar-dropdown>
      <b-navbar-dropdown label="Help" v-bind:hoverable="true">
        <b-navbar-item href="#">Support Skynet!</b-navbar-item>
        <b-navbar-item href="#">Contact Us</b-navbar-item>
        <b-navbar-item href="#">Authorship Policy</b-navbar-item>
      </b-navbar-dropdown>
    </template>
    <template slot="end">
      <b-navbar-item tag="div">
        <div class="buttons">
          <a class="button is-primary">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light">Log in</a>
          <Notifications />
        </div>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script lang="ts">
  import { Component, Prop, Vue } from "vue-property-decorator";
  import Notifications from "@/components/Notifications.vue";

  @Component({
    components: {
      Notifications
    }
  })
  export default class Navbar extends Vue {
    @Prop() private user_name!: string;
  }
</script>

<style lang="scss" scoped>
  @import "@/scss/_variables.scss";
  #skynet {
    color: $primary;
    font-weight: bold;
    padding-left: 0.4rem;
  }
</style>