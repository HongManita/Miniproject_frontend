<template>
  <v-app>
    <v-main>
      <AppBarLogin/>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import AppBarLogin from './components/AppBarLogin.vue';
export default {
  name: 'App',

  components: {
    HelloWorld,
    AppBarLogin
  },

  data: () => ({
    //
  }),
}
</script>
