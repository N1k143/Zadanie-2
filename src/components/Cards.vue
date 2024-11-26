<template>
    <div v-for="item in list" :key="item.id" class="card mt-4" style="width: 18rem;">
      <div class="card-body">
        <p class="card-text">Порядковый номер: {{ item.id }}</p>
        <p class="card-text">ФИО: {{ item.fio }}</p>
        <p class="card-text">Дата: {{ item.date }}</p>
        <p class="card-text">Количество отработанных дней: {{ item.days }}</p>
        <p class="card-text">Сумма без налоговых отчислений : {{ item.sum1 }}</p>
        <p class="card-text">Сумма с налоговыми отчислениями (-15%): {{ item.sum2 }}</p>
      </div>
      <div class="card-footer">
        <button type="button" class="btn btn-outline-danger">Удалить</button>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from "vue";
  
  export default {
    setup() {
      const list = ref([
        {
          id: 1,
          fio: "Петрунин Никита Владимирович",
          days: 1,
          date: "21.05.24",
          sum1: 1000,
          sum2: 500
        },
      ]);
  
      return {
        list,
      };
    },
  };
  </script>
  
  <style scoped>

  </style>