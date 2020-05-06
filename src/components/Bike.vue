<template>
  <router-link :to="bikePath">
    <table>
      <tr>
        <td>Name:</td>
        <td>{{ bike.Name }}</td>
      </tr>
      <tr>
        <td>Make:</td>
        <td>{{ bike.Make }}</td>
      </tr>
      <tr>
        <td>Frame:</td>
        <td>{{ bike.Frame }}</td>
      </tr>
      <tr>
        <td>Fork:</td>
        <td>{{ bike.Fork }}</td>
      </tr>
      <tr>
        <td>Headset:</td>
        <td>{{ bike.Headset }}</td>
      </tr>
      <tr>
        <td>Stem:</td>
        <td>{{ bike.Stem }}</td>
      </tr>
      <tr>
        <td>Bars:</td>
        <td>{{ bike.Bars }}</td>
      </tr>
      <tr>
        <td>Front Brake:</td>
        <td>{{ bike.Front_Brake }}</td>
      </tr>
      <tr>
        <td>Rear Brake:</td>
        <td>{{ bike.Rear_Brake }}</td>
      </tr>
      <tr>
        <td>Rear Mech:</td>
        <td>{{ bike.Rear_Mech }}</td>
      </tr>
      <tr>
        <td>Shifters:</td>
        <td>{{ bike.Shifters }}</td>
      </tr>
      <tr>
        <td>Speed:</td>
        <td>{{ bike.Speed }}</td>
      </tr>
      <tr>
        <td>Rims:</td>
        <td>{{ bike.Rims }}</td>
      </tr>
      <tr>
        <td>Front Tyre:</td>
        <td>{{ bike.Front_Tyre }}</td>
      </tr>
      <tr>
        <td>Rear Tyre:</td>
        <td>{{ bike.Rear_Tyre }}</td>
      </tr>
      <tr>
        <td>Seat Post:</td>
        <td>{{ bike.Seat_Post }}</td>
      </tr>
      <tr>
        <td>Saddle:</td>
        <td>{{ bike.Saddle }}</td>
      </tr>
      <tr>
        <td>Chainset:</td>
        <td>{{ bike.Chainset }}</td>
      </tr>
      <tr>
        <td>Bottom Bracket:</td>
        <td>{{ bike.Bottom_Bracket }}</td>
      </tr>
      <tr>
        <td>Chain:</td>
        <td>{{ bike.Chain }}</td>
      </tr>
      <tr>
        <td>Cassette:</td>
        <td>{{ bike.Cassette }}</td>
      </tr>
      <tr>
        <td>Pedals:</td>
        <td>{{ bike.Pedals }}</td>
      </tr>
    </table>

    <img :src="Image" :alt="bike.Name" />
  </router-link>
</template>

<script>
export default {
  props: ['bike'],
  computed: {
    Image: function() {
      return `${this.bike.Image}`
    },
    bikePath: function() {
      return `/bike/${this.bike.ID}`
    },
  },
}
</script>

<style scoped>
img {
  box-shadow: 0 0 35px #111;
  max-width: 11rem;
}
</style>
