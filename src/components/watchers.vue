<script setup>
import { ref, reactive, computed, watch } from "vue";

const x = ref(0);
const y = ref(10);
const sum = ref(0);

const obj = reactive({ count: 0 });

watch(x, (newX) => {
    console.log(`x is ${newX}`);
});

// геттер
// watch(
//     () => x.value + y.value,
//     (sum) => {
//         console.log(`сумма x + y равна: ${sum}`);
//     }
// );

// // массив из нескольких источников
// watch([x, () => y.value], ([newX, newY]) => {
//     console.log(`x равен ${newX} и y равен ${newY}`);
// });

// watch(obj, (newValue) => {
//     console.log("new " + newValue.count);
// });
</script>

<template>
    <ul>
        <li>
            <p>одиночный ref</p>
            <button class="btn btn-primary" @click="x++">{{ x }}</button>
        </li>
        <li>
            <p>геттер</p>
            <p>sum x + y = {{}}</p>
            <button class="btn btn-primary" @click="y += 10">{{ y }}</button>
        </li>
        <li>
            <p>массив из нескольких источников</p>

            <button class="btn btn-primary" @click="y += 10">{{ y }}</button>
            <button class="btn btn-primary" @click="x++">{{ x }}</button>
        </li>

        <li>
            <p>Глубокие наблюдатели</p>

            <button class="btn btn-primary" @click="obj.count++">
                {{ obj.count }}
            </button>
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
