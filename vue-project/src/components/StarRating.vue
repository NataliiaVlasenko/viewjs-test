<template>
  <div class="star-rating">
    <span v-for="index in starLimit" :key="index" class="star star--outlined"></span>
  </div>
  <div class="star-rating__colored" :style="ratingWidthStyle">
    <span v-for="index in rating" :key="index" class="star star--colored"></span>
  </div>
</template>

<script>
export default {
  name: 'StarRating',
  props: {
    rating: {
      type: Number,
      default: 0
    },
    starLimit: {
      type: Number,
      default: 5
    }
  },
  computed: {
    ratingWidth() {
      return (this.rating / this.starLimit) * 100
    },
    ratingWidthStyle() {
      return `width: ${this.ratingWidth}%;`
    }
  }
}
</script>

<style lang="scss" scoped>
.star-rating {
  position: relative;
  display: inline-flex;
  &__colored {
    
    position: absolute;
    width: 0;
    
    top: 0;
    left: 0;
    overflow: hidden;
  }
}
.star {
  display: inline-block;
  width: 24px;
  height: 24px;
  margin: 0 3px;
  flex-shrink: 0;
  &:first-child {
    margin-left: 0;
  }
  &--colored {
    background: url('../../src/components/icons/yellowStar.svg') center no-repeat;
  }
  &--outlined {
    background: url('../../src/components/icons/blackStar.svg') center no-repeat;
  }
}
</style>
