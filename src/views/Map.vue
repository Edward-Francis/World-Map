<template>
  <div class="Map" />
</template>

<script>
import gmapsInit from "@/utils/gmaps";
export default {
  name: "Map",
  async mounted() {
    try {
      const google = await gmapsInit();
      const geocoder = new google.maps.Geocoder();
      const map = new google.maps.Map(this.$el);

      geocoder.geocode({ address: "Europe" }, results => {
        map.setCenter(results[0].geometry.location);
        map.fitBounds(results[0].geometry.viewport);
      });
    } catch (error) {
      console.error(error);
    }
  }
};
</script>

<style>
.Map {
  width: 100vw;
  height: 100vh;
}
</style>
