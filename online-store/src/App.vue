<template>
  <div id="app" class="container my-5">
    <h1>My online store</h1>
    <div class="row">
      <Item
        v-for="item in forSale"
        :key="item.invId"
        :invId="item.invId"
        :name="item.name"
        :image="item.image"
        :price="item.price" />
    </div>
 {{ inCart }}
  </div>
</template>
<script>
import Item from './Item.vue';
export default {
  name: 'app',
  computed: {
    forSale() { return this.$store.getters.forSale; },
    inCart() { return this.$store.getters.inCart; },
  },
  components: {
    Item,
  },
};
</script>
<style>
  /* Nothing for now */
</style>