<script setup lang="ts">
import { ref, computed } from "vue";

const cooktailDataListInit: Cooktail[] = [
  { id: 2345, name: "whiteLady", price: 1200 },
  { id: 4412, name: "blueHawaii", price: 1500 },
  { id: 6792, name: "newYork", price: 1100 },
  { id: 8429, name: "martine", price: 1500 },
];
const cooktailDataList = ref(cooktailDataListInit);
const cooktail1500 = computed((): Cooktail[] => {
  const newList = cooktailDataList.value.filter(
    (cooktailItem: Cooktail): boolean => {
      return cooktailItem.price == 1500;
    }
  );
  return newList;
});

interface Cooktail {
  id: number;
  name: string;
  price: number;
}
</script>

<template>
  <section>
    <ul>
      <li v-for="cooktailItem in cooktailDataList" :key="cooktailItem.id">
        {{ cooktailItem.name }}の値段は{{ cooktailItem.price }}円
      </li>
    </ul>
  </section>
  <section>
    値段が1500円のカクテルリスト
    <ul>
      <li
        v-for="cooktailItem in cooktail1500"
        :key="cooktail1500 + cooktailItem.id"
      >
        {{ cooktailItem.name }}の値段は{{ cooktailItem.price }}円
      </li>
    </ul>
  </section>
</template>
