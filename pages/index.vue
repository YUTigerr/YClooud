<script setup lang="ts">
import { ref } from "vue";

const cooktailListInit = new Map<number, Cooktail>();
cooktailListInit.set(2345, { id: 2345, name: "whiteLady", price: 1200 });
cooktailListInit.set(4412, { id: 4412, name: "blueHawaii", price: 1500 });
cooktailListInit.set(6792, { id: 6792, name: "newYork", price: 1100 });
cooktailListInit.set(8429, { id: 8429, name: "martine", price: 1500 });
const cooktailDataList = ref(cooktailListInit);

interface Cooktail {
  id: number;
  name: string;
  price?: number;
}
</script>

<template>
  <ul>
    <li v-for="[id, cooktailItem] in cooktailDataList" :key="id">
      {{ cooktailItem.name }}の値段は{{ cooktailItem.price }}円
    </li>
  </ul>
</template>
