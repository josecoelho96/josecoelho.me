<template>
  <v-content class="hidden-sm-and-up">
    <v-card class="mx-auto" max-width="500">
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <SmallScreenTimelineItem
            v-for="(entry, index) in entries"
            :key="index"
            :entry="entry"
          />
        </v-timeline>
      </v-card-text>
    </v-card>
  </v-content>
</template>

<script>
import SmallScreenTimelineItem from "@/components/SmallScreenTimelineItem.vue";
export default {
  name: "SmallScreenTimeline",
  components: {
    SmallScreenTimelineItem
  },
  props: {
    entries: {
      type: Array,
      default: function() {
        return [];
      }
    }
  }
};
</script>
