<script setup>
import moment from 'moment';

import  Todo  from "./Todo.vue";
defineProps({
  startDate: {
    type: Date,
    required: false
  },
  withTodo: {
    type:Boolean,
    required:false
  }
});
</script>



<template>
  <!-- <div class="card mb-4">
    <header class="card-header">
      <slot name="heading"></slot>
      <p class="card-header-title">
      </p>
    </header>
    <div class="card-content">
      <div class="content">
        <p v-if="startDate">{{ waitingDays }}</p>
        <Todo v-if="withTodo" />
        <slot></slot>
      </div>
    </div>
  </div> -->
        <div>
          {{heading}}
        </div>
</template>
<script>

export default {
  props: ['startDate', 'withTodo', "heading"],
  data() {
    return {
      interval: null,
      timeRestant: null,
      joursRestant: null,
      heuresRestant: null,
      minutesRestant: null,
      secondesRestant: null,
    }
  },
  beforeDestroy() {
    // prevent memory leak
    clearInterval(this.interval)
  },
  mounted() {
    setInterval(() => this.setWaitingDays(), 1000)
  },
  methods: {
    setWaitingDays() {
      // `this` points to the component instance
      let now = moment()
      let to_date = moment(this.startDate)
      // let string = `${to_date.diff(now, "days")} J ${to_date.diff(now, "hours")} H ${to_date.diff(now, "minutes")} M ${to_date.diff(now, "seconds")}`
      this.joursRestant = Math.ceil(to_date.diff(now, "days", true)).toLocaleString();
      this.heuresRestant = Math.ceil(to_date.diff(now, "hours", true)).toLocaleString();
      this.minutesRestant = Math.ceil(to_date.diff(now, "minutes", true)).toLocaleString();
      this.secondesRestant = Math.ceil(to_date.diff(now, "seconds", true)).toLocaleString();
    }
  },

  computed: {
    // a computed getter
    waitingDays() {
    //   // `this` points to the component instance
    //   let now = moment()
    //   let to_date = moment(this.startDate)
      let string = `${this.joursRestant} J ${this.heuresRestant} H ${this.minutesRestant} M ${this.secondesRestant} S`
      return string
    }
  }
}
</script>