<template>
  <div class="container">
    <div class="map">
      <div
        v-for="(region, index) in regions"
        :key="index"
        class="region"
        :style="{
          maxWidth: region.maxWidth,
          maxHeight: region.maxHeight,
          top: region.top,
          left: region.left,
          maskImage: `url(${require('@/assets/img/regions/' + (index + 1) + '.svg')})`,
          WebkitMaskImage: `url(${require('@/assets/img/regions/' + (index + 1) + '.svg')})`
        }"
      >
        <p>{{ region.title}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { regions } from '@/data/regions';

export default {
  name: 'MapView',
  data () {
    return {
      regions
    }
  }
}
</script>

<style lang="scss">
@import "../assets/styles/components/map-view";
</style>