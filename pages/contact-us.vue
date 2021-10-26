<template>
  <div>
        <map
      :center="[54.98, 82.89]"
      :marker="[54.98, 82.89]"
      :styles="{width: '300px', height: '200px'}"
      :zoom="16"
    ></map>
  </div>
</template>

<script>
import '../components/map/map.vue'
export default {
components:{
    map
}
}
</script>

<style>

</style>