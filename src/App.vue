<template>
  <v-app id="app">
    <navBar></navBar>
    <v-main>
      <div class="content my-1" fluid>
        <router-view></router-view>
      </div>
    </v-main>
    <footBar />
  </v-app>
</template>

<script>
import navBar from '@/components/nav-bar.vue';
import footBar from '@/components/footer.vue';
export default {
  components: {
    navBar,
    footBar,
  },
  data: () => {
    return {};
  },
};
</script>
