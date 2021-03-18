<template>
  <v-card class="mt-4 pa-4">
    <v-card-subtitle>회원가입하고 <br/>쿠폰 받아가세요.</v-card-subtitle>
    <v-card-actions>
      <v-btn color="teal" rounded large class="text pa-4"><h3>회원 가입</h3></v-btn>
      <v-btn rounded large class="pa-4" @click="test"><h3>로그인</h3></v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  methods: {
    test () {
      this.$firebase.database().ref('test').set({
        title: 'abcd'
      })
    }
  }
}
</script>

<style scoped>
.text {
  color: white
}
</style>
