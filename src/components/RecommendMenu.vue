<template>
  <v-container class="mt-8">
    <h3>하임스 추천메뉴</h3>
    <div class="item_box">
      <div
        class="item"
        v-for="menu in recommendMenu"
        :key="menu.title"
      >
        <v-img
          :src="menu.subURL"
          class="rounded-circle"
          width="100"
        ></v-img>
        <h4>{{ menu.title }}</h4>
      </div>
    </div>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      recommendMenu: [],
      menuDialog: false
    }
  },
  filters: {
    comma (val) {
      return String(val).replace(/\B(?=(\d{3})+(?!\d))/g, ',')
    }
  },
  created () {
    this.getRecommendMenu()
  },
  methods: {
    getRecommendMenu () {
      this.$firebase.database().ref('RecommendMenu').on('value', (snapshot) => {
        this.recommendMenu = snapshot.val()
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
h3 {
  font-size: 1.5rem;
}
.item_box {
  display: flex;
  justify-items: center;
  margin-top: 10px;
  margin-bottom: 50px;
  overflow: auto;
  -webkit-overflow-scrolling: touch;
}
.item_box {
    -ms-overflow-style: none; /* IE and Edge */
    scrollbar-width: none; /* Firefox */
}
.item_box::-webkit-scrollbar {
    display: none; /* Chrome, Safari, Opera*/
}
.item {
  margin: 20px;
  display: flex;
  flex-direction: column;
}
.item h4 {
  text-align: center;
}
</style>
