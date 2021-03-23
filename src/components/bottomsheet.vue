<template>
  <v-bottom-sheet inset v-model="activated">
    <template v-slot:activator="{ on, attrs }">
      <v-app-bar-nav-icon v-on="on" v-bind="attrs"></v-app-bar-nav-icon>
    </template>
    <v-sheet class="pa-8 mt-auto">
      <v-row justify="start">
        <v-col cols="6" align="left">
          <div class="text-h6 font-weight-bold">Navigate Now</div>
        </v-col>
        <v-col cols="6" align="right">
          <v-btn icon @click="activated = !activated">
            <v-icon>mdi-close</v-icon>
          </v-btn>
        </v-col>
      </v-row>
      <v-row>
        <v-list-item-group>
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
        </v-list-item-group>
      </v-row>
    </v-sheet>
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
