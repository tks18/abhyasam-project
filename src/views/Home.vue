<template>
  <div class="home">
    <v-row>
      <v-col cols="12">
        <div :class="ismobile ? 'mx-4 my-3' : 'mx-10 my-8'">
          <v-row align="center" justify="center">
            <v-col :cols="ismobile ? 12 : 7" align="left">
              <div class="text-h4 font-weight-black">
                &#8220; Learning happens when it is not intended &#8221;
              </div>
              <div class="text-subtitle-1 mx-5 my-2 text-right">
                – Acharya Vinobha bave.
              </div>
            </v-col>
          </v-row>
        </div>
      </v-col>
      <v-col cols="12">
        <div class="text-center">
          <div class="text-center font-weight-bold text-h5">
            Abhyasam E-Gurukulam
          </div>
        </div>
      </v-col>
      <v-col cols="12">
        <v-card
          elevation="20"
          height="400"
          img="https://unsplash.com/photos/w8fDRpYU5oQ/download?force=true&w=1920"
          raised
        >
          <v-card-text class="inherit-height-responsive">
            <v-row align="end" class="inherit-height">
              <v-col :cols="ismobile ? 12 : 6"> </v-col>
              <v-col justify="end" :cols="ismobile ? 12 : 6">
                <v-card raised shaped>
                  <v-card-title
                    :class="
                      (ismobile ? 'text-h6' : 'text-h4') + ' font-weight-bold'
                    "
                  >
                    An Authentic Indian Lifestyle…
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
      <v-col cols="12">
        <div class="title text-center">
          <div class="sub-title text-overline">Our Workshops are Always</div>
          <div class="main-title font-weight-bold text-h4">Hands on Living</div>
        </div>
        <div class="hands-on-body">
          <v-container>
            <v-carousel
              cycle
              :height="ismobile ? null : 400"
              hide-delimiter-background
              show-arrows-on-hover
            >
              <v-carousel-item
                v-for="(card_item, index) in carousel_cards"
                v-bind:key="index"
              >
                <v-card :height="ismobile ? null : 400">
                  <v-card-text>
                    <div
                      class="text-h5 white--text my-3 font-weight-bold text-center"
                    >
                      {{ card_item.card_title }}
                    </div>
                    <v-row align="center">
                      <v-col
                        :cols="ismobile ? 12 : 8"
                        :align="ismobile ? 'center' : 'right'"
                      >
                        <v-img
                          :max-height="ismobile ? null : 300"
                          :src="card_item.body.image"
                        ></v-img>
                      </v-col>
                      <v-col
                        :cols="ismobile ? 12 : 4"
                        :class="ismobile ? 'mb-5' : ''"
                        :align="ismobile ? null : 'left'"
                      >
                        <ul>
                          <div class="text-h6 my-3 font-weight-bold">
                            Highlights
                          </div>
                          <li
                            class="text-body-1 my-1"
                            v-for="(list_text, index) in card_item.body.list"
                            v-bind:key="index"
                          >
                            {{ list_text }}
                          </li>
                        </ul>
                      </v-col>
                    </v-row>
                  </v-card-text>
                </v-card>
              </v-carousel-item>
            </v-carousel>
          </v-container>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import { ismobile } from '@/plugins/helpers';
export default {
  name: 'Home',
  data: () => {
    return {
      colors: [
        'indigo',
        'warning',
        'pink darken-2',
        'red lighten-1',
        'deep-purple accent-4',
      ],
      slides: ['First', 'Second', 'Third', 'Fourth', 'Fifth'],
    };
  },
  computed: {
    ismobile() {
      return ismobile();
    },
    carousel_cards() {
      return [
        {
          card_title: 'Ulagam',
          body: {
            list: [
              'Permaculture',
              'Home/Roof Gardening',
              'Manure Making',
              'Herbs around you',
              'Insects, birds & you',
            ],
            image:
              'https://abhyasamkshetram.files.wordpress.com/2020/12/permaculture.jpg?w=1080',
          },
        },
        {
          card_title: 'Unavu',
          body: {
            list: [
              'Traditional Indian Cooking',
              'Madhubarkam (Brewing traditional Indian beverages)',
              'Thamboolam (Paan)',
              'Ayurvedic Dieting',
              'Food – elixir & eating – penance',
            ],
            image:
              'https://abhyasamkshetram.files.wordpress.com/2020/12/home-gardening.jpg?w=1080',
          },
        },
        {
          card_title: 'Uvagai',
          body: {
            list: [
              'Pottery',
              'Clay sculpting & mural arts',
              'Your own Ganesha (Chadurthi Special)',
              'Tanjore art',
              'Tholpaavai koothu (traditional theatrics)',
            ],
            image:
              'https://abhyasamkshetram.files.wordpress.com/2020/12/manure-making.jpg?w=1080',
          },
        },
      ];
    },
  },
};
</script>
