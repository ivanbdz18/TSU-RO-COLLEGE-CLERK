<template>
  <md-card class="md-card-profile">
    <div class="md-card-avatar">
       <img class="img" :src="cardUserImage">
    </div>

    <md-card-content>
      <h6 class="category text-gray">College Clerk</h6>
      <h4 class="card-title">Shiela Mae T. Espinosa</h4>
      <md-button class="md-round md-danger">Sign Out</md-button>
    </md-card-content>
  </md-card>
</template>
<script>
export default {
  name: 'user-card',
  props: {
    cardUserImage: {
      type: String,
      default: require('@/assets/img/tsu-logo.png')
    }
  },
  data () {
    return {
    }
  }
}

</script>
<style>

</style>
