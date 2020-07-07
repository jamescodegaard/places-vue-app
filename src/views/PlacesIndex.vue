<template>
  <div class="places-index">
    <div v-for="place in places">
      <h2>{{ place.name }}</h2>
      <p>{{ place.address }}</p>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      places: []
    };
  },
  created: function() {
    axios
      .get("/api/places")
      .then(response => {
        response.data;
        this.places = response.data;
      })
      .catch();
  },
  methods: {}
};
</script>