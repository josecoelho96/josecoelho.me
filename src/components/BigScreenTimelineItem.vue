<template>
  <v-timeline-item :color="entry.color">
    <template v-slot:opposite>
      <span
        :class="`headline font-weight-bold ${entry.color}--text`"
        v-text="entry.date"
      ></span>
    </template>
    <v-card :color="entry.color" dark>
      <v-card-title class="title">{{ entry.title }}</v-card-title>
      <v-card-text class="white text--primary">
        <p>{{ entry.description }}</p>
        <v-btn
          v-if="showReadMore(entry)"
          :color="entry.color"
          class="mx-0"
          outline
        >
          Read more
        </v-btn>
      </v-card-text>
    </v-card>
  </v-timeline-item>
</template>

<script>
export default {
  name: "BigScreenTimelineItem",
  props: {
    entry: {
      type: Object,
      default: function() {
        return {
          title: "Right now",
          date: "Today",
          color: "blue",
          references: {},
          description: "Just a normal day."
        };
      }
    }
  },
  methods: {
    showReadMore: function(entry) {
      if (
        entry.references !== undefined &&
        Object.keys(entry.references).length > 0
      ) {
        return true;
      }
      return false;
    }
  }
};
</script>
