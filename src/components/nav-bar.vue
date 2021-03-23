<template>
  <v-app-bar app shaped dense elevate-on-scroll>
    <bottomBar></bottomBar>
    <v-toolbar-title class="text-title font-weight-bold">
      Abhyasam Kshetram
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn icon> <v-icon>mdi-facebook</v-icon> </v-btn>
    <v-menu transition="slide-y-transition" bottom left>
      <template v-slot:activator="{ on, attrs }">
        <v-btn icon v-bind="attrs" v-on="on">
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          shaped
          v-for="(links, index) in socials"
          @click="links.link"
          v-bind:key="index"
        >
          <v-list-item-icon>
            <v-icon>{{ links.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-title>
            {{ links.title }}
          </v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </v-app-bar>
</template>

<script>
import bottomBar from '@/components/bottomsheet';
export default {
  components: {
    bottomBar,
  },
  data: () => {
    return {
      socials: [
        {
          title: 'Twitter',
          icon: 'mdi-twitter',
          link: '',
        },
        {
          title: 'Instagram',
          icon: 'mdi-instagram',
          link: '',
        },
      ],
    };
  },
};
</script>

<style></style>
