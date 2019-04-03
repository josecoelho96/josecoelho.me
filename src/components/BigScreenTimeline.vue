<template>
  <v-content class="hidden-xs-only">
    <v-timeline>
      <BigScreenTimelineItem
        v-for="(entry, index) in entries"
        :key="index"
        :entry="entry"
      />
    </v-timeline>
  </v-content>
</template>

<script>
import BigScreenTimelineItem from "@/components/BigScreenTimelineItem.vue";

export default {
  name: "BigScreenTimeline",
  components: {
    BigScreenTimelineItem
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
