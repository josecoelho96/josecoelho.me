<template>
  <v-content class="hidden-sm-and-up">
    <v-card class="mx-auto" max-width="500">
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <v-timeline-item
            v-for="(item, index) in entries"
            :key="index"
            :color="item.color"
            small
          >
            <v-layout pt-3>
              <v-flex xs3 text-xs-center>
                <strong>{{ item.date | truncateYearMonth }}</strong>
              </v-flex>
              <v-flex xs9>
                <strong>{{ item.title }}</strong>
                <div class="caption">{{ item.description }}</div>
                <v-btn
                  v-if="showReadMore(item)"
                  :color="item.color"
                  class="mx-0"
                  outline
                >
                  Read more
                </v-btn>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-card>
  </v-content>
</template>

<script>
export default {
  name: "SmallScreenTimeline",
  filters: {
    truncateYearMonth: function(value) {
      let monthShortened = {
        January: "Jan",
        February: "Feb",
        March: "March",
        April: "April",
        May: "May",
        June: "June",
        July: "July",
        August: "August",
        September: "Sept",
        October: "Oct",
        November: "Nov",
        December: "Dec"
      };

      let date = value.split(" ");

      if (date.length === 1) {
        return value;
      } else if (date.length === 2) {
        // TODO: Truncate month, left year untouched
        if (monthShortened[date[0]] !== undefined) {
          return monthShortened[date[0]] + " " + date[1];
        } else {
          return date[0].substring(0, 5) + " " + date[1];
        }
      } else {
        if (value.length > 15) {
          value = value.substring(0, 10);
        }
        return value;
      }
    }
  },
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
