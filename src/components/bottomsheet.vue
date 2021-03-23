<template>
  <v-bottom-sheet inset v-model="activated">
    <template v-slot:activator="{ on, attrs }">
      <v-app-bar-nav-icon v-on="on" v-bind="attrs"></v-app-bar-nav-icon>
    </template>
    <v-list>
      <v-subheader>Navigate Now</v-subheader>
      <v-list-item
        v-for="(route, index) in routes"
        v-bind:key="index"
        @click="route.link"
      >
        <v-list-item-icon>
          <v-icon>{{ route.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-title> {{ route.title }} </v-list-item-title>
      </v-list-item>
    </v-list>
  </v-bottom-sheet>
</template>

<script>
export default {
  data: () => {
    return {
      activated: false,
    };
  },
  computed: {
    routes() {
      return [
        {
          title: 'Home',
          icon: 'mdi-home-circle',
          link: 'home',
        },
        {
          title: 'Blog',
          icon: 'mdi-post',
          link: 'about',
        },
      ];
    },
  },
};
</script>

<style></style>
