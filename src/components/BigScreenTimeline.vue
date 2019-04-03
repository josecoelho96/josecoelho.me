<template>
  <v-content class="hidden-xs-only">
    <v-timeline>
      <v-timeline-item
        v-for="(item, index) in entries"
        :key="index"
        :color="item.color"
      >
        <template v-slot:opposite>
          <span
            :class="`headline font-weight-bold ${item.color}--text`"
            v-text="item.date"
          ></span>
        </template>
        <v-card :color="item.color" dark>
          <v-card-title class="title">{{ item.title }}</v-card-title>
          <v-card-text class="white text--primary">
            <p>{{ item.description }}</p>
            <v-btn
              v-if="showReadMore(item)"
              :color="item.color"
              class="mx-0"
              outline
            >
              Read more
            </v-btn>
          </v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </v-content>
</template>

<script>
export default {
  name: "BigScreenTimeline",
  props: {
    entries: {
      type: Array,
      default: function() {
        return [];
      }
    }
  },
  methods: {
    showReadMore: function(item) {
      if (
        item.references !== undefined &&
        Object.keys(item.references).length > 0
      ) {
        return true;
      }
      return false;
    }
  }
};
</script>
