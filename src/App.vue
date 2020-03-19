<template>
  <div id="app">
    <h1>MOMENT SAMPLE</h1>
    <h2>現在日</h2>
    <p>{{ getTime | moment }}</p>
    <h2>生まれた日</h2>
    <p>{{ "1990-10-23 23:00:00" | moment }}</p>
    <h2>生まれてから</h2>
    <p>{{ elapsedTime(getTime , "1990-10-23") }}日</p>
  </div>
</template>

<script>
import moment from "moment"

export default {
  name: 'App',
  components: {
  },
  computed: {
    getTime() {
      return moment()
    }
  },
  methods: {
    elapsedTime(a, b) {
      return moment(a).diff(moment(b), 'days', false)
    }
  },
  filters: {
    moment(date_str) {
      moment.locale('ja')
      return moment(date_str).format('YYYY-MM-DD')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
