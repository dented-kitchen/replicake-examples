<template lang="pug">
  .add-meal
    h2 Log a meal:
    form(@submit.prevent="submit")
      ItemDatalist
      template(v-for="(item, i) in items")
        AddItem(:item="item" :index="i")
        button(type="button" @click="items.splice(i, 1)") x
        br
      button(type="button" @click="items.push({ name: 'New Item'})") +
      button(type="submit") Submit
</template>

<script>
import AddItem from './AddItem.vue';
import ItemDatalist from './ItemDatalist.vue';

export default {
  name: 'add-meal',
  components: {
    AddItem,
    ItemDatalist,
  },

  data() {
    return {
      items: [{
        name: 'New Item',
      }],
    };
  },

  methods: {
    submit() {
      console.log('submitting!');
    },
  },
};
</script>
