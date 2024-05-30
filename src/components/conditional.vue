<script setup>
import { ref, reactive, shallowRef } from "vue";
const conditionVue = ref(true);
const switchConditionVue = () => (conditionVue.value = !conditionVue.value);
</script>

<template>
    <button class="btn btn-primary" @click="switchConditionVue">Switch</button>
    <ul>
        <li>
            v-if/else
            <p v-if="conditionVue">Vue is ❤</p>
            <div v-else>
                <ul>
                    <li>Vue</li>
                    <li>is</li>
                    <li>💕</li>
                </ul>
            </div>
        </li>
        <li>
            Условные группы с помощью v-if и template
            <p v-if="conditionVue">Vue is ❤</p>
            <template v-else>
                <ul>
                    <li>Vue</li>
                    <li>is</li>
                    <li>💕</li>
                </ul>
            </template>
        </li>
        <li>
            Используйте v-show, если переключения будут частыми, и предпочитайте
            v-if, если условие может и не измениться во время исполнения.
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
