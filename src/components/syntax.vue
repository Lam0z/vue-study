<script setup>
import {ref} from 'vue'
import lesson from "./lesson.vue";

// СИНТАКСИС ШАБЛОНОВ
const rawHtml = `<span style="color: red">Красный текст.</span>`;

const dynamicId = "someText";
const bulAttr = true;
const dynamicAttributes = {
    id: "idAttribute",
    class: "btn btn-primary"
};
let number = ref(10);
const ifNumber = number>10 ? 'Больше':
        number==10 ? 'Равно':'Меньше'
const dateNow = ()=> new Date().getDate()

const seen = true;
const doSomething = ()=> number.value++


</script>

<template>
    <lesson :title="`Сырой HTML`">
        <p>Двойные фигурные скобки: {{ rawHtml }}</p>
        <p>Директива v-html: <span v-html="rawHtml"></span></p>
    </lesson>
    <lesson :title="`Атрибуты`">
        <p :id="dynamicId">Динамический атрибут ID: {{ dynamicId }}</p>
        <p :dynamicId>Одноименное сокращение :dynamicId : {{ dynamicId }}</p>
        <p>
            Булевые атрибуты:
            <button class="btn btn-primary" :disabled="bulAttr">
                {{ bulAttr }}
            </button>
        </p>
        <p>
            Динамическая привязка нескольких атрибутов через v-bind  :
            <pre class=" text-bg-info">
                const dynamicAttributes = {
                    id: "idAttribute",
                    class: "btn btn-success"
                }
            </pre>
            <button v-bind="dynamicAttributes">Text</button>
        </p>
    </lesson>

    <lesson :title="`Использование JavaScript-выражений`">
       <ul>
        <li>число {{number}} - выражение: {{ number }} + 1 =  {{ number+1 }}</li>
        <li>Условие, если 10: {{
        ifNumber
        
        }} </li>
        <li>
            Вызов функции dateNow(), сегодня день месяца: {{dateNow()}}
        </li>
       </ul>
    </lesson>

    <lesson :title="`Директивы`">
        <ul>
            <li>
                Директива v-if , seen = {{ seen=true }}
                <p v-if="seen">Сейчас меня видно</p>
            </li>
            <li>
                Директива v-on функция doSomething меняет число {{ number }}
                <button @click="doSomething"class="btn btn-primary">Клик</button>
            </li>

        </ul>
        <img src="./assets/img/visualSintax.png" alt="">
    </lesson>
</template>