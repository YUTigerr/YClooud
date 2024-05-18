<script setup lang="ts">
import {ref} from "vue";
const htmlStr = ref(`<a href="https://vuejs.org//">Vue.jsのTOPページ</a>`);
const price = ref(1000);
const hello = ref("こんにちは");
</script>

<template>
    <section>{{ htmlStr }}</section>
    <section v-html="htmlStr"></section>

    <section v-pre>
        <p @click="showHello">{{ hello! }}</p>
    </section>

    <section>
        <input type="number" v-model="price">円<br>
        <p>金額は{{ price }}円です</p>
        <p v-once>金額は{{ price }}円です</p>
    </section>

    <p v-cloak>{{ hello }}</p>
</template>

<style>
[v-cloak] {
    display: none;
}
</style>