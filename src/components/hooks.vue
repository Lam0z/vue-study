<script setup>
import { ref, reactive, computed, onMounted, onUpdated } from "vue";
onMounted(() => {
    console.log("компонент Hooks теперь примонтирован");
});
const updateTest = ref(0);

onUpdated(() => {
    console.log(
        `Хук на изменение реактивной переменной updateTest  - ${
            document.querySelector("button").textContent
        }`
    );
});
</script>

<template>
    <ul>
        <li>
            onMounted - Регистрирует коллбэк, который будет вызван после того,
            как компонент будет смонтирован
        </li>
        <li>
            onUpdated() - Регистрирует коллбэк, который будет вызван после того,
            как компонент обновит своё DOM-дерево в результате реактивного
            изменения состояния.
            <button class="btn btn-success" @click="updateTest++">
                {{ updateTest }}
            </button>
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
