<script setup lang="ts">
import { ref } from "vue";

const cooktailListInit: { [key: number]: string } = {
  2345: "ホワイトレディ",
  4412: "ブルーハワイ",
  6792: "ニューヨーク",
};
const cooktailList = ref(cooktailListInit);
</script>
<template>
  <ul>
    <li v-for="(cooktailName, id) in cooktailList" :key="'cooktailList' + id">
      IDが{{ id }}のカクテルは{{ cooktailName }}
    </li>
  </ul>
  <ul>
    <li
      v-for="(cooktailName, id, index) in cooktailList"
      :key="'cooktailListWithIdx' + id"
    >
      {{ index + 1 }}: IDが{{ id }} のカクテルは{{ cooktailName }}
    </li>
  </ul>
</template>
