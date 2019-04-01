<template>
  <v-content>
    <v-container>
      <v-layout pb-4 text-xs-center>
        <v-flex xs12>
          <h1 text-xs-center class="display-1">
            About me...
          </h1>
        </v-flex>
      </v-layout>

      <v-layout>
        <v-flex xs12 sm8 md6 offset-sm2 offset-md3 text-xs-center>
          <v-avatar size="200">
            <v-img
              class="elevation-6"
              src="/img/photo.jpg"
              aspect-ratio="1"
            ></v-img>
          </v-avatar>
          <div id="resume" class="body-1 mt-5">
            <p>
              Hi! I'm José Coelho, a Portuguese MSc student of
              <a
                href="https://fenix.tecnico.ulisboa.pt/cursos/meec"
                target="_blank"
                >Electrical Engineering and Computer Science</a
              >
              at
              <a href="https://tecnico.ulisboa.pt/en/" target="_blank"
                >Técnico Lisboa</a
              >. Currently I'm working on my MSc Thesis on
              <span class="body-2"
                >Feature Selection for Early Prediction In Multivariate Time
                Series</span
              >.
            </p>
            <p>
              I'm also a Software Engineer at
              <a href="https://www.premium-minds.com/" target="_blank"
                >Premium Minds</a
              >, a portuguese software house.
            </p>

            <p>
              Previously I was the president of
              <a href="https://neecist.org/" target="_blank">NEECIST</a>, a
              students group at my University.
            </p>
          </div>

          <div class="pt-4" @click="showTimeline = !showTimeline">
            <v-btn color="info"
              >View {{ showTimeline ? "less" : "more" }}!</v-btn
            >
          </div>
        </v-flex>
      </v-layout>

      <v-layout>
        <v-flex xs12 lg8 offset-lg2 text-xs-center>
          <v-slide-y-transition>
            <div v-show="showTimeline" id="timeline" class="pt-3">
              <div class="hidden-xs-only">
                <v-timeline align-top>
                  <v-timeline-item
                    v-for="(item, i) in timelineItems"
                    :key="i"
                    :color="item.color"
                    :icon="item.icon"
                    fill-dot
                  >
                    <v-card :color="item.color" dark>
                      <v-card-title class="title"
                        >Lorem Ipsum Dolor</v-card-title
                      >
                      <v-card-text class="white text--primary">
                        <p>
                          Lorem ipsum dolor sit amet, no nam oblique veritus.
                          Commune scaevola imperdiet nec ut, sed euismod
                          convenire principes at. Est et nobis iisque percipit,
                          an vim zril disputando voluptatibus, vix an salutandi
                          sententiae.
                        </p>
                        <v-btn :color="item.color" class="mx-0" outline>
                          Button
                        </v-btn>
                      </v-card-text>
                    </v-card>
                  </v-timeline-item>
                </v-timeline>
              </div>
              <div class="hidden-sm-and-up">
                <v-card class="mx-auto" max-width="400">
                  <v-card dark flat>
                    <v-btn absolute bottom color="pink" right fab>
                      <v-icon>mdi-plus</v-icon>
                    </v-btn>
                    <v-card-title class="pa-2 purple lighten-3">
                      <v-btn icon>
                        <v-icon>mdi-menu</v-icon>
                      </v-btn>
                      <h3 class="title font-weight-light text-xs-center grow">
                        Timeline
                      </h3>
                      <v-avatar>
                        <v-img
                          src="https://avataaars.io/?avatarStyle=Circle&topType=LongHairStraight&accessoriesType=Blank&hairColor=BrownDark&facialHairType=Blank&clotheType=BlazerShirt&eyeType=Default&eyebrowType=Default&mouthType=Default&skinColor=Light"
                        ></v-img>
                      </v-avatar>
                    </v-card-title>
                    <v-img
                      src="https://cdn.vuetifyjs.com/images/cards/forest.jpg"
                      gradient="to top, rgba(0,0,0,.44), rgba(0,0,0,.44)"
                    >
                      <v-container fill-height>
                        <v-layout align-center>
                          <strong class="display-4 font-weight-regular mr-4"
                            >8</strong
                          >
                          <v-layout column justify-end>
                            <div class="headline font-weight-light">Monday</div>
                            <div class="text-uppercase font-weight-light">
                              February 2015
                            </div>
                          </v-layout>
                        </v-layout>
                      </v-container>
                    </v-img>
                  </v-card>
                  <v-card-text class="py-0">
                    <v-timeline align-top dense>
                      <v-timeline-item color="pink" small>
                        <v-layout pt-3>
                          <v-flex xs3>
                            <strong>5pm</strong>
                          </v-flex>
                          <v-flex>
                            <strong>New Icon</strong>
                            <div class="caption">Mobile App</div>
                          </v-flex>
                        </v-layout>
                      </v-timeline-item>

                      <v-timeline-item color="teal lighten-3" small>
                        <v-layout wrap pt-3>
                          <v-flex xs3>
                            <strong>3-4pm</strong>
                          </v-flex>
                          <v-flex>
                            <strong>Design Stand Up</strong>
                            <div class="caption mb-2">Hangouts</div>
                            <v-avatar>
                              <v-img
                                src="https://avataaars.io/?avatarStyle=Circle&topType=LongHairFrida&accessoriesType=Kurt&hairColor=Red&facialHairType=BeardLight&facialHairColor=BrownDark&clotheType=GraphicShirt&clotheColor=Gray01&graphicType=Skull&eyeType=Wink&eyebrowType=RaisedExcitedNatural&mouthType=Disbelief&skinColor=Brown"
                              ></v-img>
                            </v-avatar>
                            <v-avatar>
                              <v-img
                                src="https://avataaars.io/?avatarStyle=Circle&topType=ShortHairFrizzle&accessoriesType=Prescription02&hairColor=Black&facialHairType=MoustacheMagnum&facialHairColor=BrownDark&clotheType=BlazerSweater&clotheColor=Black&eyeType=Default&eyebrowType=FlatNatural&mouthType=Default&skinColor=Tanned"
                              ></v-img>
                            </v-avatar>
                            <v-avatar>
                              <v-img
                                src="https://avataaars.io/?avatarStyle=Circle&topType=LongHairMiaWallace&accessoriesType=Sunglasses&hairColor=BlondeGolden&facialHairType=Blank&clotheType=BlazerSweater&eyeType=Surprised&eyebrowType=RaisedExcited&mouthType=Smile&skinColor=Pale"
                              ></v-img>
                            </v-avatar>
                          </v-flex>
                        </v-layout>
                      </v-timeline-item>

                      <v-timeline-item color="pink" small>
                        <v-layout pt-3>
                          <v-flex xs3>
                            <strong>12pm</strong>
                          </v-flex>
                          <v-flex>
                            <strong>Lunch break</strong>
                          </v-flex>
                        </v-layout>
                      </v-timeline-item>

                      <v-timeline-item color="teal lighten-3" small>
                        <v-layout pt-3>
                          <v-flex xs3>
                            <strong>9-11am</strong>
                          </v-flex>
                          <v-flex>
                            <strong>Finish Home Screen</strong>
                            <div class="caption">Web App</div>
                          </v-flex>
                        </v-layout>
                      </v-timeline-item>
                    </v-timeline>
                  </v-card-text>
                </v-card>
              </div>
            </div>
          </v-slide-y-transition>
        </v-flex>
      </v-layout>
    </v-container>
  </v-content>
</template>

<script>
export default {
  data: function() {
    return {
      showTimeline: false,
      timelineItems: [
        {
          color: "red lighten-2",
          icon: "star"
        },
        {
          color: "purple darken-1",
          icon: "book"
        },
        {
          color: "green lighten-1",
          icon: "email"
        },
        {
          color: "indigo",
          icon: "bookmark_border"
        }
      ]
    };
  }
};
</script>
