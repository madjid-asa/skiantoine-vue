
<script>
export default {
  data() {
    return {
      display: "hours"
    }
  },
  beforeDestroy() {},
  mounted() {
    // this.$emit("display", this.display)
  },
  methods: {},
  computed: {},
  watch:{
    display: (val, oldVal)=>{
      // this.$emit("display", val)
    }
  }
}
</script>

<template>
  <form>
  <div class="columns">
      <div id="displayInput" class="column">
        <div>Unité d'attente</div>
        <div id="control">
          <label class="radio" for="days">
            <input type="radio" id="days" value="days" v-model="display" />
            Jours
          </label>
          <label class="radio" for="hours">
            <input type="radio" id="hours" value="hours" v-model="display" />
            Heures
          </label>
          <label class="radio" for="minutes">
            <input type="radio" id="minutes" value="minutes" v-model="display" />
            Minutes
          </label>
          <label class="radio" for="seconds">
            <input type="radio" id="seconds" value="seconds" v-model="display" />
            Secondes
          </label>
        </div>
      </div>
    </div>
  </form>
</template>

<style scoped>
</style>
