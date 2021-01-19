<template>
  <div id="app">
    <!-- TODO inputで入力した際に入力した内容を受け取れる様にv-modelを使用する -->
     <input type="text" v-model="text" />
     <!-- TODO クリックイベントを作成してリクエストを送信する関数を実行 -->
  <button v-on:click="userClick">住所自動入力</button>
<!-- TODO マスタッシュ記法で住所が代入されたへ変数を描画 -->
  <p>Address:{{ text }}</p>
  </div>
</template>

<script>
  import axios from "axios";
export default {
  data() {
    return{
      text:''
    }
  },
  methods:{
    async userClick(){
      const item = await axios.get(
    'https://apis.postcode-jp.com/api/v4/.postcodes/1000001?apiKey=macrShCnuXRx72WRiphQHn2XH0nw3jVqjhbewEN'
      );
     

console.log(item);
this.text =
item.data[0].allAddress;
    }
  }
}
  </script>