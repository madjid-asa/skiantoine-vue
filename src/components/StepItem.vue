<script setup>
import moment from "moment";

import Todo from "./Todo.vue";
defineProps({
  startDate: {
    type: Date,
    required: false,
  },
  withTodo: {
    type: Boolean,
    required: false,
  },
  heading: {
    type: String,
    required: true,
  },
  display: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="card mb-4">
    <header class="card-header">
      <p class="card-header-title">
        {{ heading }}
      </p>
    </header>
    <div class="card-content">
      <div class="content">
        <p v-if="startDate">{{ waitingTime }}</p>
        <Todo v-if="withTodo" />
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
const KIND_DISPLAY = {
  days: "Jours",
  hours: "heures",
  minutes: "minutes",
  seconds: "secondes",
};
export default {
  props: ["startDate", "withTodo", "heading", "display"],
  data() {
    return {
      interval: null,
      timeRestant: null,
      joursRestant: null,
      heuresRestant: null,
      minutesRestant: null,
      secondesRestant: null,
    };
  },
  beforeDestroy() {
    // prevent memory leak
    clearInterval(this.interval);
  },
  mounted() {
    setInterval(() => this.setWaitingDays(), 1000);
  },
  methods: {
    setWaitingDays() {
      // `this` points to the component instance
      let now = moment();
      let to_date = moment(this.startDate);
      // let string = `${to_date.diff(now, "days")} J ${to_date.diff(now, "hours")} H ${to_date.diff(now, "minutes")} M ${to_date.diff(now, "seconds")}`
      if (this.display) {
        this.timeRestant = Math.ceil(
          to_date.diff(now, this.display, true)
        ).toLocaleString();
      }
      // this.heuresRestant = Math.ceil(
      //   to_date.diff(now, "hours", true)
      // ).toLocaleString();
      // this.minutesRestant = Math.ceil(
      //   to_date.diff(now, "minutes", true)
      // ).toLocaleString();
      // this.secondesRestant = Math.ceil(
      //   to_date.diff(now, "seconds", true)
      // ).toLocaleString();
    },
  },

  computed: {
    // a computed getter
    waitingTime: function () {
      //   // `this` points to the component instance
      //   let now = moment()
      //   let to_date = moment(this.startDate)
      // let string = `${this.joursRestant} J ${this.heuresRestant} H ${this.minutesRestant} M ${this.secondesRestant} S`
      console.log(this.$props, this.display);
      let displayWitingTime = `${this.timeRestant} ${
        KIND_DISPLAY[this.$props.display]
      }`;
      return displayWitingTime;
    },
  },
};
</script>
