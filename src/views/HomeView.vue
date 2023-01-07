<script setup>
import StepList from "../components/StepList.vue";
import Config from "../components/Config.vue";
</script>

<template>
  <main>
    <section class="section">
      <div class="container">
        <Config @display="this.setDisplay" />
        <StepList :display="this.displayKind" />
      </div>
    </section>
  </main>
</template>

<script>
export default {
  props: [],
  components: { Config, StepList },
  data() {
    return {
      displayKind: "hours",
    };
  },
  methods: {
    setDisplay: function (val) {
      this.displayKind = val;
    },
  },
};
</script>
