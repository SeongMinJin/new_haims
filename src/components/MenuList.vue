<template>
  <v-card>{{ category }}</v-card>
</template>

<script>
export default {
  props: [
    'category'
  ],
  data () {
    return {
      menu: [],
      currentCategory: ''
    }
  },
  created () {
  },
  methods: {
    getCurrentCategory () {
      this.$firebase.database().ref('Menu/Drink').child()
    }
  }
}
</script>
