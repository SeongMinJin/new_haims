<template>
  <div>
    <v-stepper v-model="e1" class="container">
      <v-stepper-items>
        <v-stepper-content step="1" class="stepper_container">
          <div class="sub_container" @click="loadMenuList(2)">
            <v-img
              class="rounded-circle"
              src="@/assets/americano.jpg"
              contain
              max-width="100"
            ></v-img>
            <h3>커피</h3>
          </div>
          <div class="sub_container" @click="loadMenuList(3)">
            <v-img
              class="rounded-circle"
              src="@/assets/americano.jpg"
              contain
              max-width="100"
            ></v-img>
            <h3>라떼</h3>
          </div>
          <div class="sub_container" @click="loadMenuList(4)">
            <v-img
              class="rounded-circle"
              src="@/assets/americano.jpg"
              contain
              max-width="100"
            ></v-img>
            <h3>차</h3>
          </div>
          <div class="sub_container mb-12" @click="loadMenuList(5)">
            <v-img
              class="rounded-circle"
              src="@/assets/americano.jpg"
              contain
              max-width="100"
            ></v-img>
            <h3>주스/에이드</h3>
          </div>
        </v-stepper-content>

        <v-stepper-content
          step="2"
          class="stepper_container"
        >
          <div class="d-flex">
            <v-btn
              color="gray"
              @click="e1 = 1"
              icon
              left
            >
              <v-icon>mdi-arrow-left</v-icon>
            </v-btn>
            <v-spacer></v-spacer>
            <h4 class="d-flex align-center">{{this.currentCategory}}</h4>
          </div>
          <div
            v-for="(menu, i) in category"
            :key="menu.title"
            class="menu_container"
            @click="openMenuDialog(i)"
          >
            <v-img
              :src="menu.subURL"
              class="rounded-circle"
              contain
              max-height="100"
              max-width="100"
            ></v-img>
            <div class="text_box">
              <h3>{{ menu.title }}</h3>
              <h4>{{ menu.price | comma }}원</h4>
            </div>
          </div>
        </v-stepper-content>
      </v-stepper-items>
    </v-stepper>
    <v-dialog
      v-model="menuDialog"
      fullscreen
      hide-overlay
      transition="dialog-bottom-transition"
    >
      <v-app-bar
        height="250"
      >
        <v-img
          :src="selectedMenu.mainURL"
          contain
        ></v-img>
      </v-app-bar>
      <v-card>
        <v-btn x-large icon @click="menuDialog=false"><v-icon>mdi-close</v-icon></v-btn>
        <v-card-title><h2>{{ selectedMenu.title }}</h2></v-card-title>
        <v-card-text><h4>{{ selectedMenu.description }}</h4></v-card-text>
        <v-card-text><h1>{{ selectedMenu.price }}</h1></v-card-text>
      </v-card>
      <v-bottom-navigation fixed class="d-flex align-center" height="100">
        <v-card @click="openKaKao" color="teal" height="45" width="300" rounded="pill" dark class="d-flex justify-center align-center">주문하기</v-card>
      </v-bottom-navigation>
    </v-dialog>
  </div>
</template>
<script>
export default {
  components: {
  },
  data () {
    return {
      category: [],
      e1: 1,
      currentCategory: 'null',
      menuDialog: false,
      currentIndex: '',
      selectedMenu: []
    }
  },
  created () {
  },
  filters: {
    comma (val) {
      return String(val).replace(/\B(?=(\d{3})+(?!\d))/g, ',')
    }
  },
  methods: {
    loadMenuList (i) {
      this.e1 = 2
      if (i === 2) {
        this.currentCategory = 'Coffee'
      } else if (i === 3) {
        this.currentCategory = 'Latte'
      } else if (i === 4) {
        this.currentCategory = 'Tea'
      } else {
        this.currentCategory = 'Ade'
      }
      this.$firebase.database().ref('Menu/Drink').child(this.currentCategory).on('value', (snapshot) => {
        this.category = snapshot.val()
      })
    },
    openMenuDialog (title) {
      this.menuDialog = true
      this.$firebase.database().ref('Menu/Drink').child(this.currentCategory).child(title).once('value', (snapshot) => {
        this.selectedMenu = snapshot.val()
      })
    },
    openKaKao () {
      var url = 'https://pf.kakao.com/_xjfxixcK'
      window.open(url)
      this.drawer = false
    }
  }
}
</script>

<style scoped>
.stepper_container {
  background-color: #f9fbe7;
}
.sub_container {
  display: flex;
  margin: 10px;
}
.sub_container h3 {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 20px;
  color: #424242;
}
.menu_container {
  display: flex;
  margin: 10px;
}
.text_box {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: flex-start;
  margin-left: 20px;
}
</style>
