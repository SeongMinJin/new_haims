<template>
  <v-container class="mt-8">
    <h3>하임스 추천메뉴</h3>
    <div class="item_box">
      <div class="item">
        <v-fab-transition>
          <v-btn
            color=""
            fab
            @click="openDialog"
          >
            <v-icon>mdi-plus</v-icon>
          </v-btn>
        </v-fab-transition>
      </div>
    </div>
    <v-dialog
      v-model="dialog"
    >
      <v-card>
        <v-app-bar
          color="red"
          dark
        >
          <v-btn icon @click="dialog = false"><v-icon>mdi-close</v-icon></v-btn>
          <v-spacer></v-spacer>
          <v-btn icon>저장</v-btn>
        </v-app-bar>
        <v-text-field
          v-model="recommendMenuTitle"
          placeholder="메뉴 이름을 입력하세요."
          class="mr-4 ml-4"
        >
        </v-text-field>
        <v-file-input
          v-model="recommendMenuImage"
          placeholder="사진을 선택 해주세요."
          prepend-icon="mdi-image"
          class="ml-4 mr-4"
        >
        </v-file-input>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      dialog: false,
      recommendMenuTitle: '',
      recommendMenuImage: []
    }
  },
  methods: {
    openDialog () {
      this.dialog = true
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
}
.text_box {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}
</style>
