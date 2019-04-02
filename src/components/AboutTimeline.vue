<template>
  <v-container>
    <v-layout>
      <v-flex text-xs-center xs12>
        <v-btn color="info" @click="timelineToggle()"
          >View {{ showTimeline ? "less" : "more" }}!</v-btn
        >
      </v-flex>
    </v-layout>
    <v-layout id="timeline">
      <v-flex xs12 lg8 offset-lg2 text-xs-center>
        <v-slide-y-transition>
          <div v-show="showTimeline" class="pt-3">
            <SmallScreenTimeline />
            <BigScreenTimeline />
          </div>
        </v-slide-y-transition>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import goTo from "vuetify/lib/components/Vuetify/goTo";

import SmallScreenTimeline from "@/components/SmallScreenTimeline.vue";
import BigScreenTimeline from "@/components/BigScreenTimeline.vue";

export default {
  name: "AboutTimeline",
  components: {
    SmallScreenTimeline,
    BigScreenTimeline
  },
  data: function() {
    return {
      showTimeline: false
    };
  },
  methods: {
    timelineToggle: function() {
      this.showTimeline = !this.showTimeline;
      const timelineOptionsShow = {
        duration: 1000,
        offset: 70,
        easing: "easeInOutCubic"
      };
      const timelineOptionsHide = {
        duration: 500,
        offset: 0,
        easing: "easeInOutCubic"
      };

      if (this.showTimeline === true) {
        goTo(document.getElementById("timeline"), timelineOptionsShow);
      } else {
        goTo(document.getElementById("top"), timelineOptionsHide);
      }
    }
  }
};
</script>
