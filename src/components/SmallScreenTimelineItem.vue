<template>
  <v-timeline-item :color="entry.color" small>
    <v-layout pt-3>
      <v-flex xs3 text-xs-center>
        <strong>{{ entry.date | truncateYearMonth }}</strong>
      </v-flex>
      <v-flex xs9>
        <strong>{{ entry.title }}</strong>
        <div class="caption">{{ entry.description }}</div>
        <v-btn
          v-if="showReadMore(entry)"
          :color="entry.color"
          class="mx-0"
          outline
        >
          Read more
        </v-btn>
      </v-flex>
    </v-layout>
  </v-timeline-item>
</template>

<script>
export default {
  name: "SmallScreenTimelineItem",
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
