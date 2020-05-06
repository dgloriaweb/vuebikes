<template>
  <div>
    <ul>
      <li v-for="item in bike.results" :key="item.Name">
        <ul>
          <li>Name: {{ item.Name }}</li>
          <li>Make: {{ item.Make }}</li>
          <li>Frame: {{ item.Frame }}</li>
          <li>Fork: {{ item.Fork }}</li>
          <li>Headset: {{ item.Headset }}</li>
          <li>Stem: {{ item.Stem }}</li>
          <li>Bars: {{ item.Bars }}</li>
          <li>Front Brake: {{ item.Front_Brake }}</li>
          <li>Rear Brake: {{ item.Rear_Brake }}</li>
          <li>Rear Mech: {{ item.Rear_Mech }}</li>
          <li>Shifters: {{ item.Shifters }}</li>
          <li>Speed: {{ item.Speed }}</li>
          <li>Rims: {{ item.Rims }}</li>
          <li>Front Tyre: {{ item.Front_Tyre }}</li>
          <li>Rear Tyre: {{ item.Rear_Tyre }}</li>
          <li>Seat Post: {{ item.Seat_Post }}</li>
          <li>Saddle: {{ item.Saddle }}</li>
          <li>Chainset: {{ item.Chainset }}</li>
          <li>Bottom Bracket: {{ item.Bottom_Bracket }}</li>
          <li>Chain: {{ item.Chain }}</li>
          <li>Cassette: {{ item.Cassette }}</li>
          <li>Pedals: {{ item.Pedals }}</li>
          <li>Image: {{ item.Image }}</li>
          <img :src="item.Image" :alt="item.Name" />
          <li></li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'BikesList',
  data() {
    return {
      bike: {
        Name: '',
        Make: '',
        Frame: '',
        Fork: '',
        Headset: '',
        Stem: '',
        Bars: '',
        Front_Brake: '',
        Rear_Brake: '',
        Rear_Mech: '',
        Shifters: '',
        Speed: '',
        Rims: '',
        Front_Tyre: '',
        Rear_Tyre: '',
        Seat_Post: '',
        Saddle: '',
        Chainset: '',
        Bottom_Bracket: '',
        Chain: '',
        Cassette: '',
        Pedals: '',
        Image: 'image/jpg',
      },
    }
  },
  computed: {
    image: function() {
      return `${this.bike.image}`
    },
    moviePath: function() {
      return `/movie/${this.movie.id}`
    },
  },
  created: function() {
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

<style scoped>
li {
  text-align: left;
}
</style>
