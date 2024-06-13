<script setup>
import { ref, reactive, computed } from "vue";
const message = ref("");
const check = ref(true);
const checkedNames = ref([]);
const picked = ref("");
const selected = ref("");
const selectedMultiple = ref([]);

const selectedD = ref("A");

const options = ref([
    { text: "Один", value: "A" },
    { text: "Два", value: "B" },
    { text: "Три", value: "C" },
]);
const toggle = ref("");
const truevalue = "Yes";
const falsevalue = "No";

const selectedSomevalue = ref(null);

const modNumbers = ref(null);
const modTrim = ref(null);
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
        <li>
            <p>Выпадающие списки</p>
            <div>Выбрано: {{ selected }}</div>

            <select class="form-select" v-model="selected">
                <option selected disabled value="">
                    Выберите один из вариантов
                </option>
                <option>А</option>
                <option>Б</option>
                <option>В</option>
            </select>

            <div>
                Выбраны:
                <ul>
                    <template v-if="!selectedMultiple.length">
                        <p>Элементы не выбраны</p>
                    </template>
                    <template v-else>
                        <li v-for="item in selectedMultiple" :key="item">
                            {{ item }}
                        </li>
                    </template>
                </ul>
            </div>

            <select class="form-select" v-model="selectedMultiple" multiple>
                <option>А</option>
                <option>Б</option>
                <option>В</option>
            </select>
        </li>
        <li>
            <p>Динамическое отображение списка опций с помощью v-for:</p>
            <p>Выбрано {{ selectedD }}</p>
            <select v-model="selectedD">
                <option
                    v-for="item in options"
                    :key="item.value"
                    :value="item.value"
                >
                    {{ item.text }}
                </option>
            </select>
        </li>

        <li>
            <ul>
                <li>
                    <p>Привязка значений false-value и true-value</p>
                    <p>Choosed: {{ toggle }}</p>
                    <label for="tf">
                        <input
                            id="tf"
                            class="form-check-input"
                            type="checkbox"
                            v-model="toggle"
                            :true-value="truevalue"
                            :false-value="falsevalue"
                        />
                        Toggle</label
                    >
                </li>
                <li>
                    <p>Выпадающие списки</p>
                    <p>Выбрано {{ selectedSomevalue }}</p>
                    <select v-model="selectedSomevalue">
                        <!-- инлайновый объект с данными -->
                        <option :value="{ number: 123 }">123</option>
                        <option :value="{ number: 345 }">345</option>
                        <option :value="{ number: 567 }">567</option>
                    </select>
                </li>
            </ul>
        </li>
        <li>
            <p>Модификаторы</p>
            <p>Number : {{ modNumbers }}</p>
            <input v-model.number="modNumbers" />
            <p>Trim : {{ modTrim }}</p>
            <input v-model.trim="modTrim" />
        </li>
    </ul>
</template>

<style lang="scss" scoped></style>
