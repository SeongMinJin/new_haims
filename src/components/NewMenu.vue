<template>
  <div>
    <v-card
      class="mt-4"
      height="400"
    >
      <v-img
        height="400"
        contain
        :src="newMenuImageURL"
      ></v-img>
    </v-card>
  </div>
</template>
<script>
export default {
  data () {
    return {
      newMenuImageURL: ''
    }
  },
  created () {
    this.$firebase.database().ref('NewMenu').child('NewMenuImage').on('value', (snapshot) => {
      this.newMenuImageURL = snapshot.val().imgURL
    })
  },
  methods: {
  }
}
</script>
