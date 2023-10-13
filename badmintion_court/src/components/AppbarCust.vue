<template>
  <div>
    <v-layout>
      <v-app-bar :elevation="2" app color="#E7DDF9">
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title>My files</v-toolbar-title>
      </v-app-bar>

      <v-navigation-drawer v-model="drawer" location="top" temporary>
            <v-list
          :items="items"
        ></v-list>
      </v-navigation-drawer>
    </v-layout>
  </div>
</template>


<script>
export default {
  methods: {
    register() {
      this.$router.push({ path: "/register" }).catch(() => {});
    },
    login() {
      this.$router.push({ path: "/login" }).catch(() => {});
    }
  },
  data: () => ({
    drawer: false,
    group: null,
    items: [
      {
        title: "Foo",
        value: "foo"
      },
      {
        title: "Bar",
        value: "bar"
      },
      {
        title: "Fizz",
        value: "fizz"
      },
      {
        title: "Buzz",
        value: "buzz"
      }
    ]
  }),
  watch: {
      group () {
        this.drawer = false
      },
    },

};
</script>
<style scoped>
.text-BadCourt {
  color: #8b47fa;
}
.button-login {
  border-radius: 15px;
  margin-right: 1%;
}

.text-login {
  color: #fff;
}

.button-regis {
  border-radius: 15px;
  border: 2px solid #8b47fa;
}

.text-regis {
  color: #8b47fa;
}
.burger-icon {
  color: #8b47fa;
}
</style>
