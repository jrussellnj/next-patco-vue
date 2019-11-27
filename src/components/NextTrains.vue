<template>
  <div>
    <h1>{{ direction }}</h1>

    <ul>
      <li v-for="t in times" v-bind:key="t.trip_id">
        {{ t.departure_time }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'NextTrains',
  props: [
    'direction',
    'times'
  ]
}
</script>
