<template>
  <StepItem
    :display="this.display"
    :startDate="new Date('01/07/2023 05:30')"
    :withTodo="true"
    :heading="'Depart Maison'"
  />
  <StepItem
    :display="this.display"
    :startDate="new Date('01/07/2023 06:40')"
    heading="Départ du train"
  >
    <!-- Direction Peisey Vallandry ! -->
  </StepItem>

  <StepItem
    :display="this.display"
    :startDate="new Date('01/07/2023 11:48')"
    heading="Arrivée gare saint maurice"
  >
  </StepItem>
  <StepItem
    :display="this.display"
    :startDate="new Date('01/07/2023 14:30')"
    heading="Taxi"
  >
  </StepItem>
  <StepItem
    :display="this.display"
    :startDate="new Date('01/07/2023 15:30')"
    heading="Arrivée châlet"
  >
  </StepItem>
  <StepItem
    :display="this.display"
    :startDate="new Date('01/08/2023 09:00')"
    heading="Première descente"
  >
  </StepItem>
  <StepItem
    :display="this.display"
    :startDate="new Date('01/13/2023 16:50')"
    heading="Dernière descente"
  >
  </StepItem>
  <StepItem
    :display="this.display"
    :startDate="new Date('01/14/2023 12:30')"
    heading="Quitte le châlet"
  >
  </StepItem>
  <StepItem
    :display="this.display"
    :startDate="new Date('01/14/2023 15:30')"
    heading="Train du retour"
  >
  </StepItem>
</template>

<script>
import StepItem from "./StepItem.vue";

export default {
  name: "StepList",
  props: ["display"],
  components: {
    StepItem,
  },
  mounted() {
    return {};
  },
};
</script>
