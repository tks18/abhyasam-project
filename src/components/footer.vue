<template>
  <v-footer elevation="12">
    <v-row align="center" class="my-3">
      <v-col cols="12" align="center">
        <v-btn v-for="icon in icons" :key="icon" class="mx-4" icon>
          <v-icon size="24px">
            {{ icon }}
          </v-icon>
        </v-btn>
      </v-col>
      <v-col cols="12" align="center">
        There is never been a better time to rediscover the value of life.
        Abhyasam means working with nature. We’re coming into a fantastic time
        of original India.
      </v-col>
      <v-col cols="12" align="center">
        <div class="text-h6 font-weight-black">
          Abhyasam | <v-icon>mdi-copyright</v-icon
          >{{ ' ' + new Date().getFullYear() }}
        </div>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    icons: ['mdi-facebook', 'mdi-twitter', 'mdi-linkedin', 'mdi-instagram'],
  }),
};
</script>

<style></style>
