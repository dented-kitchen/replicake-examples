<template lang="pug">
  .add-item
    .search-or-new
      input(list="items" :id="`name-${index}`" placeholder="Search existing")
      span or
      button(type="button" @click="create = true") Add new item
    CreateIngredient(v-if="create" :id="index")
</template>

<script>
import CreateIngredient from './CreateIngredient.vue';

export default {
  name: 'add-item',
  components: {
    CreateIngredient,
  },

  props: {
    item: Object,
    index: Number,
  },

  data() {
    return {
      name: this.item.name,
      create: false,
    };
  },

};
</script>
