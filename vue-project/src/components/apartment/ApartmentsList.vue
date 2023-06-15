<template>
  <container>
    <slot name="title"></slot>
    <div class="apartments-list">
      <template v-for="apartment in items">
        <slot name="apartment" v-bind:apartment="apartment"></slot>
      </template>
    </div>
  </container>
</template>

<script>

import container from '../shared/Container.vue'
export default {
  name: 'ApartmentsList',
  components: {
    
    container
  },
  props: {
    items: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style lang="scss" scoped>
.apartments-list {
  display: flex;
  flex-wrap: wrap;
  margin-left: -15px;
  margin-right: -15px;
  width: 100%;
}
</style>