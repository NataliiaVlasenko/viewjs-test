<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  //   defineProps({
  //   msg: {
  //     type: String,
  //     required
  //   }
  // })
  // `mounted` is a lifecycle hook which we will explain later
  mounted() {
    // `this` refers to the component instance.
    console.log(this.count) // => 1

    // data can be mutated as well
    //this.count = 2
  },
  computed() {
    return this.count
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>

<template>
  <button name="button" type="button" class="btn" @click="increment">
    <slot>
      <!-- {{ msg }} -->
      Count is: {{ count }}
    </slot>
  </button>
</template>

<style lang="scss" scoped>
.btn {
  background-color: yellowgreen;
  display: flex;
  align-items: center;
  margin-left: 30px;
  border: none;
}
</style>
