<script setup>
import { ref, reactive,computed } from "vue";
const items = ref([{ message: "Foo" }, { message: "Bar" }]);
const myObject = reactive([
    {
        title: "How to do lists in Vue",
        author: "Jane Doe",
        publishedAt: "2016-04-10",
        isComplete: false,
    },
    {
        title: "How to do lists in Vue!!!!!!!!!!",
        author: "JaAaaane sDoe",
        publishedAt: "20126-024-102222",
        isComplete: true,
    },
]);
const mas = ref([1,2,3,4,5,6,7,8,9,10])
const evenNumbers = computed(() => {
  return mas.value.filter((n) => n % 2 === 0)
})
// const multyMas = ref([1,2,3,4,5,6],[7,8,9,10,11,12])
// function even(numbers) {
//   return numbers.filter((number) => number % 2 === 0)
// }
</script>

<template>
    <ul>
        <li>
            Отображение элементов массива через v-for
            <p v-for="(item, index) in items" :key="index">
                {{ item }} {{ index }} {{ item.message }}
            </p>
        </li>
        <li>
            Отображение свойств объекта через v-for (value, key, index)
            <p v-for="(item, index, id) in myObject" :key="index">
                {{ item }} - {{ index }}- {{ id }}
                    <p v-for="obj in item" :key="obj">
                        {{ obj }}
                    </p>
            </p>
        </li>
        <li>
            v-for и диапазоны
            <span v-for="i in 20">{{ i }}</span>
        </li>
        <li>
            v-for и v-if
                <p v-for="(item, index, id) in myObject" :key="index">
                    <p v-if="item.isComplete">{{item}}</p> 
            </p>    
           
        </li>
        <li >Отображение отфильтрованных/отсортированных результатов
            <p v-for="i in evenNumbers" :key="i">{{ i }}</p>

        </li>
        <!-- <li >Множественный массив массивов отсортированный по четности
            <ul v-for="numbers in multyMas">
                <li v-for="n in even(numbers)">{{ n }}</li>
            </ul>
        </li> -->
       
    </ul>
</template>

<style lang="scss" scoped></style>
