<script setup>
import CollectionList from '@/components/CollectionList.vue'
import { ref } from 'vue'

const parameters = [
    {
        title: 'Разработка',
        obj: [
            {
                name: 'Разработка на Angular',
                date: '21.10.23',
                link: 'https://github.com/mamoudou-tr35'
            },
            {
                name: 'Разработка на React',
                date: '23.10.23',
                link: 'https://react.dev/'
            },
            {
                name: 'Разработка на Vue',
                date: '21.10.23',
                link: 'https://ru.vuejs.org/'
            },
            {
                name: 'Разработка на ванильном js',
                date: '21.10.23',
                link: 'https://github.com/mamoudou-tr35'
            },
        ]
    },
    {
        title: 'Валидация',
        obj: [
            {
                name: 'Проверка валидности',
                date: '25.10.23',
                link: 'https://validator.w3.org/'
            },
            {
                name: 'Проверка валидности введенных данных',
                date: '27.10.23',
                link: 'https://github.com/mamoudou-tr35'
            },
        ]
    },
    {
        title: 'Обновление',
        obj: [
            {
                name: 'Обновление программ',
                date: '30.10.23',
                link: 'https://validator.w3.org/'
            },
        ]
    },
    {
        title: 'Тестирование',
        obj: [
            {
                name: 'Автоматические тесты',
                date: '25.10.23',
                link: 'https://learn.javascript.ru/testing'
            },
            {
                name: 'Ручное тестирование',
                date: '27.10.23',
                link: 'https://github.com/mamoudou-tr35'
            },
            {
                name: 'Просто проверить приложение',
                date: '22.10.23',
                link: 'https://habr.com/ru/companies/vk/articles/466879/'
            },
            {
                name: 'Тщательное тестирование',
                date: '21.10.23',
                link: 'https://github.com/mamoudou-tr35'
            },
        ]
    },
]

const flag = ref(false)

function toggleFlag() {
    return flag.value = !flag.value
}

</script>

<template>
<div class="container">
    <div class="container__img">
        <img src="./assets/img/list1.png" alt="logo">
    </div>
    <div class="container__list">
        <h1 class="container__list_title" @click="toggleFlag">Список этапов разработки</h1>
        <ul v-show="flag" class="container__list_list">
            <CollectionList
                v-for="parameter in parameters"
                :key="parameter.title"
                :parameter="parameter"
            />
        </ul>
    </div>

    <h2 class="container__title2">{{ parameters.length }}</h2>
</div>
</template>

<style lang="scss" scoped>
@import "./assets/styles/main";

.container {
    display: flex;
    margin: 30px auto;
    gap: 20px;
    align-items: flex-start;
    justify-content: center;

    &__title2 {
        padding: 10px 20px;
        font-size: 24px;
        border-radius: 50%;
        border: 6px solid $red;
        color: $red;
    }

    &__list {
        cursor: pointer;
        &_title {
            font-size: 32px;
            margin-bottom: 50px;
        }
    }
}


</style>
