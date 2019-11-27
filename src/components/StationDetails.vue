<template>
  <div>
    <h1>{{ times.stationName }}</h1>

    <NextTrains
      direction="Philadelphia"
      v-bind:times="times.toPhiladelphia"
    />

    <NextTrains
      direction="Lindenwold"
      v-bind:times="times.toLindenwold"
    />
  </div>
</template>

<script>
import NextTrains from './NextTrains.vue'

export default {
  name: 'StationDetails',
  data() {
    return {
      times: []
    }
  },
  components: {
    NextTrains
  },
  mounted: function() {
    this.getTimes();
  },
  methods: {
    getTimes: async function() {
      const response = await fetch('http://localhost:3001/api/station/times?stationSlug=' + this.$route.params.stationSlug, { mode: 'cors' });
      const times = await response.json();

      console.log(times);

      /*eslint no-console: ["error", { allow: ["warn", "log"] }] */
      console.log(times);

      this.times = times;
    }
  }
}
</script>
