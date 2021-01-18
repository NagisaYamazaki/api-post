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
      "prefCode": string,
  "cityCode": string,
  "postcode": string,
  "oldPostcode": string,
  "pref": string,
  "city": string,
  "town": string,
  "allAddress": string,
  "office": string,
  "hiragana": {
    "pref": string,
    "city": string,
    "town": string,
    "office": string,
    "allAddress": string
  },
  "halfWidthKana": {
    "pref": string,
    "city": string,
    "town": string,
    "office": string,
    "allAddress": string
  },
  "fullWidthKana": {
    "pref": string,
    "city": string,
    "town": string,
    "office": string,
    "allAddress": string
  },
  "generalPostcode": boolean,
  "officePostcode": boolean,
  "location": {
    "latitude": number,
    "longitude": number
  }
},
    }
  text (){
    return this.data
  }
  
  async created() {
    const item = await axios.get('https://apis.postcode-jp.com/api/v4/postcodes/1000001 macrShCnuXRx72WRiphQHn2XH0nw3jVqjhbewEN'
    );
  }
  </script>