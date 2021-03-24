<template>
  <div class="home">
    <v-row>
      <v-col cols="12">
        <div :class="ismobile ? 'mx-4 my-3' : 'mx-10 my-8'">
          <v-row align="center" justify="center">
            <v-col :cols="ismobile ? 12 : 7" align="left">
              <div class="text-h4 font-weight-black">
                &#8220;Learning happens when it is not intended&#8221;
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
      <v-col cols="12" class="mx-2">
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
              :cycle="cycle_on"
              :height="ismobile ? null : 400"
              hide-delimiter-background
              hide-delimiters
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
                      <v-tooltip top transition="slide-y-transition">
                        <template v-slot:activator="{ on, attrs }">
                          <v-col
                            v-on="on"
                            v-bind="attrs"
                            :cols="ismobile ? 12 : 8"
                            :align="ismobile ? 'center' : 'right'"
                          >
                            <v-dialog
                              persistent
                              transition="slide-y-transition"
                            >
                              <template v-slot:activator="{ on, attrs }">
                                <v-img
                                  v-on="on"
                                  v-bind="attrs"
                                  @click="
                                    cycle_on = false;
                                    print(cycle_on);
                                  "
                                  :height="ismobile ? null : 300"
                                  contain
                                  class="round-it-off"
                                  :alt="card_item.body.image"
                                  :src="card_item.body.image"
                                ></v-img>
                              </template>
                              <template v-slot:default="dialog">
                                <v-card>
                                  <v-card-title>
                                    <v-row>
                                      <v-col cols="8">
                                        Gallery - {{ card_item.card_title }}
                                      </v-col>
                                      <v-col cols="4" align="right">
                                        <v-btn
                                          color="error"
                                          icon
                                          @click="
                                            cycle_on = true;
                                            dialog.value = false;
                                          "
                                        >
                                          <v-icon>mdi-close</v-icon>
                                        </v-btn>
                                      </v-col>
                                    </v-row>
                                  </v-card-title>
                                  <v-card-text>
                                    <v-carousel
                                      cycle
                                      continuous
                                      hide-delimiter-background
                                      :height="ismobile ? null : 450"
                                      hide-delimiters
                                    >
                                      <v-carousel-item
                                        v-for="(images, index) in card_item.body
                                          .gallery"
                                        v-bind:key="index"
                                      >
                                        <v-img
                                          :height="ismobile ? null : 450"
                                          contain
                                          :src="images"
                                        ></v-img>
                                      </v-carousel-item>
                                    </v-carousel>
                                  </v-card-text>
                                </v-card>
                              </template>
                            </v-dialog>
                          </v-col>
                        </template>
                        <span>Click here for More Photos</span>
                      </v-tooltip>
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
      <v-col cols="12">
        <v-card
          dark
          elevation="0"
          flat
          img="https://unsplash.com/photos/odxB5oIG_iA/download?force=true&w=1920"
        >
          <v-card-text class="py-8">
            <v-container class="my-8 back-blur">
              <v-row align="center" class="my-8 white--text">
                <v-col cols="12" align="center">
                  <div class="text-body-1 font-weight-bold">Meet us Better</div>
                </v-col>
                <v-col cols="12" align="center">
                  <div class="text-h4 font-weight-bold">
                    We will show you the actual living
                  </div>
                </v-col>
                <v-col cols="12" align="center">
                  <v-row align="center">
                    <v-col
                      :cols="ismobile ? 12 : 3"
                      v-for="(info, index) in site_info_nos"
                      v-bind:key="index"
                    >
                      <div class="text-h4 font-weight-bold">{{ info.nos }}</div>
                      <div class="text-subtitle-1 font-weight-bold">
                        {{ info.title }}
                      </div>
                    </v-col>
                  </v-row>
                </v-col>
              </v-row>
            </v-container>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12">
        <v-container>
          <v-card flat>
            <v-card-text>
              <v-row align="center">
                <v-col cols="12">
                  <v-row align="center">
                    <v-col
                      :cols="ismobile ? 12 : 5"
                      :align="ismobile ? 'center' : 'right'"
                    >
                      <v-avatar size="250">
                        <v-img :src="abhyasam_photos[1]"></v-img>
                      </v-avatar>
                    </v-col>
                    <v-col
                      :cols="ismobile ? 12 : 7"
                      :align="ismobile ? 'center' : 'left'"
                    >
                      <div class="title my-2">
                        <div class="text-subtitle-1">
                          It’s more than a school
                        </div>
                        <div class="text-h4 font-weight-black">
                          It's Abhyasam
                        </div>
                      </div>
                      <div class="text-subtitle-2">
                        <span
                          class="text-elem"
                          v-for="(content, index) in abhyasam_content"
                          v-bind:key="index"
                        >
                          {{ content }}
                        </span>
                      </div>
                    </v-col>
                  </v-row>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-container>
      </v-col>
      <v-col cols="12">
        <v-container>
          <v-card dark color="primary">
            <v-card-text>
              <v-row align="center" class="my-2">
                <v-col cols="12" align="center">
                  <div class="text-title text-h4 font-weight-black white--text">
                    Abhyasam E-gurukulam
                  </div>
                  <div class="text-subtitle-1 font-weight-bold">
                    A digital dive into the depths of Indian wisdom
                  </div>
                </v-col>
                <v-col cols="12" align="center">
                  <iframe
                    :width="ismobile ? null : 750"
                    :height="ismobile ? null : 422"
                    src="https://www.youtube.com/embed/HEAZmrAyvN4"
                    title="YouTube video player"
                    frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen
                  ></iframe>
                </v-col>
                <v-col cols="12" align="center">
                  <v-btn
                    @click="
                      gotourl(
                        'https://www.youtube.com/channel/UChMMMTQubBnU77coE-3nwdg',
                      )
                    "
                  >
                    More Videos
                  </v-btn>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-container>
      </v-col>
      <v-col cols="12" class="mx-3 my-3">
        <v-row justify="center" align="center">
          <v-col
            v-for="(rating, index) in abhyasam_ratings"
            v-bind:key="index"
            :cols="ismobile ? 12 : 3"
          >
            <v-card raised>
              <v-card-text class="text-center">
                <v-row align="center">
                  <v-col cols="12" class="mb-0 pb-0 text-h6 font-weight-bold">
                    &#8220;{{ rating.title }}&#8221;
                  </v-col>
                  <v-col cols="12" class="my-0 py-0">
                    <v-rating
                      :value="rating.rate"
                      color="yellow darken-3"
                      background-color="grey darken-1"
                      empty-icon="$ratingFull"
                      readonly
                    ></v-rating>
                  </v-col>
                  <v-col cols="12" class="my-0 py-1 text-subtitle-1">
                    {{ rating.review }}
                  </v-col>
                  <v-col cols="12" class="my-0 py-1 text-h6 font-weight-bold">
                    {{ rating.by }}
                  </v-col>
                </v-row>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
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
      cycle_on: true,
    };
  },
  methods: {
    print(object) {
      console.log(object);
    },
    gotourl(url) {
      window.open(url);
      return;
    },
  },
  computed: {
    ismobile() {
      return ismobile();
    },
    abhyasam_ratings() {
      return [
        {
          rate: 5,
          title: 'Excellent Service',
          review:
            'Their service is brilliant! I really hope some of them are now using your service',
          by: 'Fauna',
        },
        {
          rate: 5,
          title: 'Love the flexibility',
          review:
            'We are very happy with the box and we value that we can have the standard box or choose our own.',
          by: 'Joseph',
        },
        {
          rate: 4,
          title: 'Fantastic quality',
          review:
            'I’m really appreciating the quality and presentation. The flavour of the veg is outstanding.',
          by: 'Michelle',
        },
      ];
    },
    site_info_nos() {
      return [
        {
          nos: 350,
          title: 'Visitors per Month',
        },
        {
          nos: 23,
          title: 'Experts Working',
        },
        {
          nos: 55,
          title: 'Off-Schoolers',
        },
        {
          nos: '100%',
          title: 'Satisfied Lifestyle',
        },
      ];
    },
    abhyasam_content() {
      return [
        'Swim and understand density, buoyancy, turbulence and the Chemistry of H2O.',
        'Play Veena and learn the physics of frequency, decibles, amplitude, along with Anandhabhairavi',
        'Express the Sakuntalam and Salt satyagraha in mudras and adavus.',
        'Laser focus, firmness & flexibility! Arjuna what are you seeing? the bird’s eye Acharya!',
        'What about your kid? Where is the actual learning?',
      ];
    },
    abhyasam_photos() {
      return [
        'https://unsplash.com/photos/-i9y9aRuqn4/download?force=true&w=1920',
        'https://unsplash.com/photos/mG1mJ7bSWXw/download?force=true&w=1920',
        'https://unsplash.com/photos/YJ7hkGdg_xg/download?force=true&w=1920',
      ];
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
              'https://unsplash.com/photos/Hcfwew744z4/download?force=true&w=1920',
            gallery: [
              'https://unsplash.com/photos/DkEJKHwgxKw/download?force=true&w=1920',
              'https://unsplash.com/photos/MhDiW1c73GI/download?force=true&w=1920',
              'https://unsplash.com/photos/oHH5Q0NpDgM/download?force=true&w=1920',
            ],
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
              'https://unsplash.com/photos/BbSBf5uv50A/download?force=true&w=1920',
            gallery: [
              'https://unsplash.com/photos/DkEJKHwgxKw/download?force=true&w=1920',
              'https://unsplash.com/photos/MhDiW1c73GI/download?force=true&w=1920',
              'https://unsplash.com/photos/oHH5Q0NpDgM/download?force=true&w=1920',
            ],
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
              'https://unsplash.com/photos/HEOMIp2FXKE/download?force=true&w=1920',
            gallery: [
              'https://unsplash.com/photos/DkEJKHwgxKw/download?force=true&w=1920',
              'https://unsplash.com/photos/MhDiW1c73GI/download?force=true&w=1920',
              'https://unsplash.com/photos/oHH5Q0NpDgM/download?force=true&w=1920',
            ],
          },
        },
      ];
    },
  },
};
</script>
