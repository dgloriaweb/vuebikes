<template>
  <div>
    bikes list
  </div>
</template>

<script>
export default {
  name: 'BikesList',
  data() {
      return {
          bike: {}
      }
  },
  created : function() {
      this.fetchData()
  },
  methods: {
    fetchData: async function() {
      try {
        const res = await fetch(
          // 'https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=ec5dc58dd49114aa47aebd1659fef849'
          // 'https://herokutestnodecrashcourse.herokuapp.com/bikes.json'
          //the above didn't work because of the browser's CORS policy, with cors_anywhere extension, this works.
          'https://limitless-peak-43368.herokuapp.com/https://herokutestnodecrashcourse.herokuapp.com/bikes.json'
        )
        const bike = await res.json()
        this.bike = bike
      } catch (e) {
        console.log(e)
      }
    },
  },
}
</script>

<style lang="scss" scoped></style>
