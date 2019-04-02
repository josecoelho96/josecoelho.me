<template>
  <v-content>
    <v-container id="top" text-xs-center>
      <h1 class="display-1">About me...</h1>
    </v-container>
    <AboutResume />
    <AboutTimeline />
  </v-content>
</template>

<script>
import AboutResume from "@/components/AboutResume.vue";
import AboutTimeline from "@/components/AboutTimeline.vue";

export default {
  name: "About",
  components: {
    AboutResume,
    AboutTimeline
  }
};
</script>
