<script >
import StepItem from './StepItem.vue'
import { RiHomeLine } from "vue-remix-icons";
export default {

}
</script>

<template>
  <StepItem :startDate="new Date('01/07/2023 05:30')" :withTodo="true" heading="Depart Maison"/>
    <!-- okook -->

  <StepItem :startDate="new Date('01/07/2023 06:40')" heading="Départ du train">
    <!-- Direction Peisey Vallandry ! -->
  </StepItem>

  <StepItem :startDate="new Date('01/07/2023 11:30')" heading="Arrivée gare saint maurice">
  </StepItem>
  <StepItem :startDate="new Date('01/07/2023 14:30')" heading="Taxi">
  </StepItem>
  <StepItem :startDate="new Date('01/07/2023 15:30')" heading="Arrivée châlet">
  </StepItem>
  <StepItem :startDate="new Date('01/08/2023 09:00')" heading="Première descente">
  </StepItem>
  <StepItem :startDate="new Date('01/13/2023 16:50')" heading="Dernière descente">
  </StepItem>
  <StepItem :startDate="new Date('01/14/2023 12:30')" heading="Quitte le châlet">
  </StepItem>
  <StepItem :startDate="new Date('01/14/2023 15:30')" heading="Train du retour">
  </StepItem>

  </template>
