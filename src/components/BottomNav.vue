<template>
  <v-bottom-navigation
  fixed
  class="d-flex justify-space-around align-center"
  height="60"
  >
    <v-btn
    plain
    color="teal"
    fab
    large
    to="/"
    >
      <span>Home</span>
      <v-icon>mdi-home</v-icon>
    </v-btn>

    <v-btn
    plain
    color="teal"
    fab
    to="/order"
    >
      <span>Order</span>
      <v-icon>mdi-coffee</v-icon>
    </v-btn>

    <v-btn
    plain
    color="teal"
    fab
    to="/coupon"
    >
      <span>Coupon</span>
      <v-icon>mdi-ticket</v-icon>
    </v-btn>

    <v-btn
    plain
    color="teal"
    fab
    to="other"
    >
      <span>Other</span>
      <v-icon>mdi-dots-horizontal</v-icon>
    </v-btn>
  </v-bottom-navigation>
</template>
