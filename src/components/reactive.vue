<script setup>
import { ref, reactive, shallowRef } from "vue";
const count = ref(0);
const state = reactive({
    count1: 1,
    count: {
        count2: 2,
    },
});

console.log(count, state);
</script>

<template>
    <ul>
        <li>
            Реактивность при помощи:
            <pre>import {ref,reactive,shallowRef} from 'vue'</pre>
        </li>
        <li>Пример с ref() в шаблоне {{ count }}</li>
        <li>Пример с reactive() в шаблоне {{ state.count1 + 1 }}</li>
        <li>
            Пример с reactive() в шаблоне для вложенных объектов
            {{ state.count.count2 + 1 }}
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
