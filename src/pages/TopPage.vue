<script lang="ts" setup>
import { reactive } from "vue";

//ユーザー名の入力値を保持するためnameという状態を保持する
const state = reactive({ name: "" });

//上記のname値の値をaleatで表示する関数（今後ゲームページに遷移するための関数として利用）
const startGame = () => {
  alert(`ユーザー名:${state.name}`);
};
</script>

<template>
  <h1>トップ画面</h1>
  <p>{{ state.name }}</p>
  <input
    v-model="state.name"
    type="text"
    placeholder="名前を入力してください(10文字以内)"
    maxlength="10"
  /><br /><br />
  <button @click="startGame()">ゲームスタート</button>
</template>

<!-- state.name 確認用のタグのスタイルを指定する -->
<style scoped>
input {
  width: 18em;
  font-size: 1.1em;
  text-align: center;
}

p {
  font-size: 1.6em;
  font-weight: bold;
  height: 5vh;
}
</style>
