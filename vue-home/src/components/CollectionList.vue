<script setup>
import {ref} from 'vue'

defineProps({
    parameter: {
        type: Object,
        required: true
    }
})

const smallFlag = ref(false)

function toggleFlag() {
    return smallFlag.value = !smallFlag.value
}
</script>

<template>
  <li class="list">
      <div class="list__head" @click="toggleFlag">
          <div class="list__head_title">{{ parameter.title }}</div>
          <div class="list__head_counter">{{ parameter.obj.length }}</div>
      </div>
      <ul class="list__list" v-show="smallFlag">
          <li class="list__list_item" v-for="(item, index) in parameter.obj" :key="item.name">
              <div class="list__list_item-count">{{ index + 0 }}/{{ parameter.obj.length }}</div>
              <div class="list__list_item-name">Тема: {{ item.name }}</div>
              <div class="list__list_item-date">Срок выполнения: {{ item.date }}</div>
              <div class="list__list_item-link">
                  <a :href="item.link" target="_blank" :title="item.link">Более подробная информация</a>
              </div>
          </li>
      </ul>
  </li>
</template>

<style lang="scss" scoped>
@import "../assets/styles/main";

.list {
  margin-bottom: 20px;
  padding: 15px;
  background: rgb(218,141,70);
  background: linear-gradient(90deg, rgba(218,141,70,0.8077004483433998) 0%, rgba(57,129,194,1) 38%, rgba(0,255,247,1) 100%);

    &__head {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-bottom: 20px;

      &_title {
        font-size: 30px;
      }

      &_counter {
        font-size: 26px;
        padding: 6px 15px;
        border-radius: 50%;
        border: 3px solid $red;
        color: $red;
      }
    }

  &__list {
    background: rgb(218,186,70);
    background: linear-gradient(90deg, rgba(218,186,70,0.8077004483433998) 0%, rgba(194,178,57,1) 38%, rgba(254,255,0,1) 100%);
    padding-top: 20px;
    padding-bottom: 20px;
    padding-right: 10px;

    &_item {
      margin-bottom: 15px;
      position: relative;

      &-count {
        position: absolute;
        top: 0;
        left: -40px;
        color: #030a3b;
        font-size: 11px;
        font-weight: 700;
      }

      &-name {
        color: $red;
        font-size: 22px;
      }

      &-link {
        color: #0d21b0;
        font-size: 16px;
      }
    }

  }


}
</style>