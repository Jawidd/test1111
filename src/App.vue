<template>
  <v-app>
    <!--  <router-link to="/component">cmp</router-link> -->
    <router-link to="/">home</router-link>
    <hr />
    <router-view />
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    //
  })
};
</script>
