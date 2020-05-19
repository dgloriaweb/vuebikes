<template>
    <div >
        <h1>{{ bike.Name }}</h1>
        <h3>Make: {{ bike.Make }}</h3>
        <p>{{ bike.Frame }}</p>
      </div>
</template>

<script>
    export default {
        data() {
    return {
      bike: {},
    }
  },
  created: function() {
    this.fetchData()
  },
   methods: {
    fetchData: async function() {
      try {
        const res = await fetch(
          // `https://api.themoviedb.org/3/movie/${this.$route.params.id}?api_key=ec5dc58dd49114aa47aebd1659fef849`

`http://localhost/larticles/public/api/article/$1`)
        const movie = await res.json()
        this.movie = movie
      } catch (e) {
        console.log(e)
      }
    },
  },
    }
</script>

<style lang="scss" scoped>

</style>