<template>
  <v-app id="app">
    <navBar></navBar>
    <v-main>
      <div class="content mx-2 my-1" fluid>
        <router-view></router-view>
      </div>
    </v-main>
  </v-app>
</template>

<script>
import navBar from '@/components/nav-bar.vue';
export default {
  components: {
    navBar,
  },
  data: () => {
    return {};
  },
};
</script>
