<template>
  <div>
    <img v-if="pokemon" :src="pokemon.sprites.front_default" alt="Pokemon Image">
    <p class="chrome-text" v-if="pokemon">{{ pokemon.name }}</p>
  </div>
  <div>
    <img v-if="pokemon2" :src="pokemon2.sprites.front_default" alt="Pokemon Image2">
    <p class="chrome-text" v-if="pokemon2">{{ pokemon2.name }}</p>
  </div>
</template>

<script setup>
const { data: pokemon } = await useFetch('https://pokeapi.co/api/v2/pokemon/1')
const { data: pokemon2 } = await useFetch("https://pokeapi.co/api/v2/pokemon/2"); // ポケモンID 1 (フシギダネ) を取得
</script>
<style>
.chrome-text {
  flex: auto;
  font-family: 'Impact', sans-serif; /* または他の太字フォント */
  font-size: 2em; /* サイズを大きく */
  color: #fff; /* 文字色を白に */
  background: linear-gradient(45deg, #808080, #c0c0c0, #fff); /* 銀色のグラデーション */
  -webkit-background-clip: text; /* 背景を文字にクリップ */
  color: transparent; /* 文字色を透明に */
}
</style>