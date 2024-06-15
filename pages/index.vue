<script setup lang="ts">
import { ref } from "vue";

const cooktailListInit = new Map<number, string>();
cooktailListInit.set(2345, "ホワイトレディ");
cooktailListInit.set(4412, "ブルーハワイ");
cooktailListInit.set(6792, "ニューヨーク");
const cooktailList = ref(cooktailListInit);
</script>
<template>
  <ul>
    <li v-for="[id, cooktaiName] in cooktailList" :key="id">
      IDが{{ id }}のカクテルは{{ cooktaiName }}です
    </li>
  </ul>
</template>
