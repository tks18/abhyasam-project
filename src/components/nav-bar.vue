<template>
  <v-app-bar app dense elevate-on-scroll>
    <bottomBar></bottomBar>
    <v-toolbar-title class="text-title font-weight-bold">
      {{ ismobile ? 'Abhyasam' : 'Abhyasam Kshetram' }}
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn
      v-for="(links, index) in socials"
      v-bind:key="index"
      @click="links.link"
      icon
    >
      <v-icon>{{ links.icon }}</v-icon>
    </v-btn>
  </v-app-bar>
</template>

<script>
import { ismobile } from '@/plugins/helpers';
import bottomBar from '@/components/bottomsheet';
export default {
  components: {
    bottomBar,
  },
  data: () => {
    return {
      socials: [
        {
          title: 'Facebook',
          icon: 'mdi-facebook',
          link: '',
        },
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
  computed: {
    ismobile() {
      return ismobile();
    },
  },
};
</script>

<style></style>
