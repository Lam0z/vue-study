<script setup>
import { ref, reactive, computed, onMounted, onUpdated } from "vue";

const input = ref(null);
const listRefs = ref([]);

const list = ref([
    { name: "Nick", sname: "Efimo" },
    { name: "Semen", sname: "Eremov" },
    { name: "Vladmir", sname: "Efstigneev" },
    { name: "Park", sname: "Huiirov" },
]);
onMounted(() => {
    input.value.focus();
    listRefs.value;
});
</script>

<template>
    <ul>
        <li>
            <p>Доступ к ссылкам</p>
            <input value="asdf" class="form-control" type="text" ref="input" />
        </li>
        <li>
            <p>Использование внутри v-for</p>
            <ul>
                <li v-for="(item, idx) in list" :key="idx" ref="listRefs">
                    {{ idx }} - {{ item.name }}
                </li>
            </ul>
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
