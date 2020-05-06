<template>
  <div>
    <div v-for="bike in bikes" :key="bike.id">
      <Bike :bike="bike" />
    </div>
  </div>
</template>

<script>
import Bike from './Bike.vue'
export default {
  name: 'BikesList',
  data() {
    return {
      bikes: [],
    }
  },
  created: function() {
    this.fetchData()
  },
  methods: {
    fetchData: async function() {
      try {
        const res = await fetch(
          // 'https://herokutestnodecrashcourse.herokuapp.com/bikes.json'
          //the above didn't work because of the browser's CORS policy, with cors_anywhere extension, this works.
          'https://limitless-peak-43368.herokuapp.com/https://herokutestnodecrashcourse.herokuapp.com/bikes.json'
        )
        const bikes = await res.json()
        this.bikes = bikes.results
      } catch (e) {
        console.log(e)
      }
    },
  },
  components: {
    Bike,
  },
}
</script>

<style scoped>
li {
  text-align: left;
}
</style>
