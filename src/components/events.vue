<script setup>
import { ref, reactive, computed } from "vue";
const count1 = ref(0);

const name = ref("Vue.js");

function greet(event) {
    alert(`Привет, ${name.value}!`);
    // `event` — нативное событие DOM

    alert(event.target.tagName);
    alert(event.target.tagname);
}

const say = (message) => alert(message);

const inlineEvent = (message, e) => {
    alert(message);
    alert(e.target.dataset.info);
};

const inputEvent = ref("");
const enter = (e) => {
    inputEvent.value = e.target.value;
};
</script>

<template>
    <ul>
        <li>
            <p>Обработчик события в виде инлайн-кода: @click="count++"</p>
            <button class="btn btn-primary" @click="count1++">+</button>
            <p>Counter: {{ count1 }}</p>
        </li>
        <li>
            <p>Вызов методов в инлайн-обработчиках</p>
            <button class="btn btn-primary" @click="say('привет')">
                Скажи привет
            </button>
            <button class="btn btn-primary" @click="say('пока')">
                Скажи пока
            </button>
        </li>
        <li>
            <p>Доступ к событию через аргумент в инлайн-обработчиках</p>

            <button
                class="btn btn-primary"
                data-info="You clicked on this button"
                @click="inlineEvent('Вы кликнули', $event)"
            >
                click
            </button>
        </li>
        <li>
            <p class="text-truncate">
                Модификаторы клавиш ctrl+enter: {{ inputEvent }}
            </p>
            <input
                type="text"
                :value="inputEvent"
                @keyup.ctrl.enter="enter"
                class="form-control"
            />
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
