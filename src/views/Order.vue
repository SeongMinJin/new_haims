<template>
  <div class="order">
    <v-card>
      <v-toolbar
        color="teal"
        dark
        flat
        prominent
      >
        <v-toolbar-title><h2>Order</h2></v-toolbar-title>

      </v-toolbar>

      <v-tabs
        v-model="tab"
        color="teal"
      >
        <v-tabs-slider color="teal"></v-tabs-slider>

        <v-tab
          v-for="item in items"
          :key="item"
        >
          {{ item }}
        </v-tab>
      </v-tabs>

      <v-tabs-items v-model="tab">
        <v-tab-item
          v-for="item in items"
          :key="item"
        >
          <Drink v-if="item === '음료'"></Drink>
        </v-tab-item>
      </v-tabs-items>
    </v-card>
  </div>
</template>

<script>
import Drink from '@/components/Drink.vue'

export default {
  name: 'Order',
  components: {
    Drink
  },
  data () {
    return {
      category: [],
      tab: null,
      items: [
        '음료', '제과류'
      ]
    }
  },
  created () {

  },
  methods: {
  }
}
</script>

<style scoped>
</style>
