<template lang="pug">
  datalist(id="items")
    option(value="Create new")
    template(v-for="item in items")
      option(:value="item.name")
</template>

<script>
export default {
  name: 'item-datalist',

  // props: {
  //   items: Array,
  // },

  data() {
    return {
      items: [
        {
          name: 'Egg',
        },
        {
          name: 'Bread (Whole Wheat)',
        },
      ],
    };
  },
};
</script>
