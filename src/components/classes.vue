<script setup>
import { ref, computed } from "vue";
const isDanger = ref(true);
const isInfo = ref(true);
const attrClasses = { "bg-danger": isDanger, "text-white": isDanger };
const attrClassesArr = [
    "bg-info ",
    { "text-danger": isInfo },
    isInfo ? "text-decoration-underline" : "",
];

const activeColor = ref("red");
const fontSize = ref(30);
const bgSuccess = "background: orange";
</script>

<template>
    <ul>
        <li>
            <p>Объектный синтаксис</p>
            <pre>{ 'bg-danger': isDanger, 'text-white': isDanger }</pre>
            <div class="p-2" :class="attrClasses">
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                Maxime, pariatur.
            </div>
        </li>
        <li>
            <p>Синтаксис с массивом</p>
            <pre class="text-truncate">
["bg-info ", { "text-danger": isInfo }, isInfo?'text-decoration-underline':'']</pre
            >
            <div class="p-2" :class="attrClassesArr">
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                Maxime, pariatur.
            </div>
        </li>
        <li>
            <p>Привязка инлайн-стилей</p>
            <pre>
                ctiveColor = ref("red");
                ontSize = ref(30);
                gSuccess = "background: orange";
            </pre>
            <div
                class="p-2"
                :style="[
                    bgSuccess,
                    { color: activeColor, fontSize: fontSize + 'px' },
                ]"
            >
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                Maxime, pariatur.
            </div>
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
