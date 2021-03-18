<template>
  <div class="other">
    <v-list-item @click="ToYoutube">
      <v-list-item-icon>
        <v-icon x-large color="red">mdi-youtube</v-icon>
      </v-list-item-icon>
      <v-list-item-content>
        <v-list-item-title>하임스 유튜브</v-list-item-title>
      </v-list-item-content>
    </v-list-item>
    <v-list-item @click="ToInstagram">
      <v-list-item-icon>
        <v-icon x-large color="purple">mdi-instagram</v-icon>
      </v-list-item-icon>
      <v-list-item-content>
        <v-list-item-title>하임스 인스타그램</v-list-item-title>
      </v-list-item-content>
    </v-list-item>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Other',
  components: {
  },
  data () {
    return {

    }
  },
  methods: {
    ToYoutube () {
      var url = 'https://www.youtube.com/channel/UCsgCW2WGxdpxsBEO59OUFqA'
      window.open(url)
    },
    ToInstagram () {
      var url = 'https://www.instagram.com/ha_tae_hatae/'
      window.open(url)
    },
    click (item) {
      console.log('hiu')
    }
  }
}
</script>

<style scoped>
* {
  background-color: #f9fbe7;
}
.other {
  height: auto;
}
.list {
  display: flex;
  align-items: center;
}
</style>
