<template>
  <v-app>
    <v-container class="main_container">
      <v-card>
        <router-view/>
        <bottom-nav></bottom-nav>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
import BottomNav from '@/components/BottomNav.vue'
export default {
  name: 'App',
  components: {
    BottomNav
  },
  mounted () {
  }
}
</script>

<style scoped>
.main_container{
  max-width: 600px;
}
</style>
