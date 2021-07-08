<template lang="pug">
  .create-ingredient
    ul
      li
        input(v-model="name")
      li
        label(:for="`calories-${id}`") Calories:
        input(v-model.number="nutrition.calories" :id="`calories-${id}`" type="number")
      li
        label(:for="`fat-${id}`") Fat:
        input(v-model.number="nutrition.fat" :id="`fat-${id}`" type="number")
      li
        label(:for="`carbs-${id}`") Carbs:
        input(v-model.number="nutrition.carbs" :id="`carbs-${id}`" type="number")
      li
        label(:for="`protein-${id}`") Protein:
        input(v-model.number="nutrition.protein" :id="`protein-${id}`" type="number")
</template>

<script>
import Replicake from 'replicake';

export default {
  name: 'create-ingredient',

  props: [
    'id',
  ],

  data() {
    return {
      name: 'New ingredient',
      nutrition: new Replicake.Nutrition(),
    };
  },

};
</script>
