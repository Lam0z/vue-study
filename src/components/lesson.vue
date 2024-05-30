<script setup>
import { ref } from "vue";
const props = defineProps({
    title: {
        type: String,
        default: "Lesson Name",
    },
});
const show = ref(true);
const toggleShow = () => (show.value = !show.value);
</script>
<template>
    <div class="lesson">
        <div class="container">
            <div class="alert alert-success fw-bold" @click="toggleShow">
                {{ title }}
            </div>

            <div class="alert alert-primary" v-show="show">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>
