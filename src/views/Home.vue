<template>
  <v-container
  class="d-flex justify-center flex-column container"
  >
    <v-container class="mt-12">
      <h1>안녕하세요. <br/> 하임스입니다.</h1>
    </v-container>
    <sign-up-banner></sign-up-banner>
    <new-menu></new-menu>
    <recommend-menu></recommend-menu>
  </v-container>
</template>

<script>
import SignUpBanner from '@/components/SignUpBanner.vue'
import NewMenu from '@/components/NewMenu.vue'
import RecommendMenu from '@/components/RecommendMenu.vue'
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    SignUpBanner,
    NewMenu,
    RecommendMenu
  },
  data () {
    return {
    }
  }
}
</script>
<style scoped>
.container{
  background-color: #f9fbe7;
}

</style>
