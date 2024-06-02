<script setup>
import { ref, reactive, computed } from "vue";
const message = ref("");
const check = ref(true);
const checkedNames = ref([]);
</script>

<template>
    <ul>
        <li>
            Обычное использование
            <p>Сообщение: {{ message }}</p>
            <input
                class="form-control"
                v-model="message"
                placeholder="отредактируй меня"
            />
        </li>
        <li>
            <span>Многострочное сообщение:</span>
            <p>{{ message }}</p>
            <textarea
                v-model="message"
                placeholder="введите несколько строчек"
            ></textarea>
        </li>
        <li>
            <span>Чекбоксы:</span>
            <p>{{ check }}</p>
            <input
                class="form-check-input"
                type="checkbox"
                v-model="check"
                id="c1"
            />
            <label for="c1" class="form-check-label">check</label>
        </li>
        <li>
            <div>Отмеченные имена: {{ checkedNames }}</div>

            <input
                type="checkbox"
                id="jack"
                value="Jack"
                v-model="checkedNames"
            />
            <label for="jack">Jack</label>

            <input
                type="checkbox"
                id="john"
                value="John"
                v-model="checkedNames"
            />
            <label for="john">John</label>

            <input type="checkbox" id="mike" value="" v-model="checkedNames" />
            <label for="mike">Mike</label>
        </li>
        <li>
            <div>Выбрано: {{ picked }}</div>

            <input type="radio" id="one" value="Один" v-model="picked" />
            <label for="one">Один</label>

            <input type="radio" id="two" value="Два" v-model="picked" />
            <label for="two">Два</label>
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
