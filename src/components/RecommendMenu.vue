<template>
  <v-container class="mt-8">
    <h3>하임스 추천메뉴</h3>
    <div class="item_box">
      <div class="item">
        <v-img
        src="@/assets/americano.jpg"
        class="rounded-circle"
        width="150"></v-img>
        <div class="text_box">
          <h4>아이스 아메리카노</h4>
        </div>
      </div>
      <div class="item">
        <v-img
        src="@/assets/americano.jpg"
        class="rounded-circle"
        width="150"></v-img>
        <div class="text_box">
          <h4>아이스 아메리카노</h4>
        </div>
      </div>
      <div class="item">
        <v-img
        src="@/assets/americano.jpg"
        class="rounded-circle"
        width="150"></v-img>
        <div class="text_box">
          <h4>아이스 아메리카노</h4>
        </div>
      </div>
    </div>
  </v-container>
</template>

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
