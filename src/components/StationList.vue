<template>
  <div class="station-list">
    <div v-for="s in stations" v-bind:key="s.stop_id">
      <router-link v-bind:to="s.slug">{{ s.stop_name }}</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StationList',
  data() {
    return {
      stations: []
    }
  },
  mounted: function() {
    this.getStation();
  },
  methods: {
    getStation: async function() {
      const response = await fetch('http://localhost:3001/api/stations', { mode: 'cors' });
      const stations = await response.json();

      /*eslint no-console: ["error", { allow: ["warn", "log"] }] */
      console.log(stations);

      this.stations = stations;
    }
  }
}
</script>
