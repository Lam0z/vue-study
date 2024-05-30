<script setup>
import { ref, reactive, computed } from "vue";
const author = reactive({
    name: "John Doe",
    books: [
        "Vue 2 - Advanced Guide",
        "Vue 3 - Basic Guide",
        "Vue 4 - The Mystery",
    ],
});
const publishedBooksMessage = computed(() => {
    return author.books.length > 0 ? "Yes" : "No";
});
</script>

<template>
    <ul>
        <li>
            <p>Есть опубликованные книги:</p>
            <span>{{ publishedBooksMessage }}</span>
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
