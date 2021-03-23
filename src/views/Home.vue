<template>
  <div class="home">
    <v-row>
      <v-col cols="12">
        <v-card
          height="300"
          img="https://abhyasamkshetram.files.wordpress.com/2020/12/ayurveda-1.jpg"
          raised
        >
          <v-card-text class="inherit-height-responsive">
            <v-row align="end" class="inherit-height">
              <v-col cols="6"></v-col>
              <v-col justify="end" cols="6">
                <v-card raised shaped>
                  <v-card-title class="text-h4">
                    An authentic Indian Lifestyle…
                  </v-card-title>
                  <v-card-subtitle>
                    Join us to enjoy the fullest living experience with load of
                    Indian values and virtues
                  </v-card-subtitle>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'Home',
};
</script>
