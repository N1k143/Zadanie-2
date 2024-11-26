<template>
  <h1 class="text-center">Cтраница учета заработной платы сотрудников</h1>
  <Forma :addWorker="addWorker"/>
  
  <div v-for="worker in workers" :key="worker.id" class="card mt-4" style="width: 18rem;">
    <div class="card-body">
      <p class="card-text">Порядковый номер: {{ worker.id }}</p>
      <p class="card-text">ФИО: {{ worker.fio }}</p>
      <p class="card-text">Дата: {{ worker.date }}</p>
      <p class="card-text">Количество отработанных дней: {{ worker.days }}</p>
      <p class="card-text">Сумма без налоговых отчислений : {{ worker.sum1 }}</p>
      <p class="card-text">Сумма с налоговыми отчислениями (-15%): {{ worker.sum2 }}</p>
    </div>
    <div class="card-footer">
      <button type="button" class="btn btn-outline-danger" @click="removeWorker(worker.id)">Удалить</button>
    </div>
  </div>

  <h1 class="text-end">Общая сумма: {{ totalSum }} тг</h1>
  <h1 class="text-end">Общая сумма с налоговыми отчислениями (-15%): {{ totalSum2 }} тг</h1>
</template>

<script>
import Forma from "./components/Forma.vue";

export default {
  components: { Forma },
  data() {
    return {
      workers: [],
      totalSum: 0,
      totalSum2: 0
    };
  },
  methods: {
    addWorker(val) {
      const newWorker = {
        id: this.workers.length + 1,
        fio: val.fio,
        date: val.date,
        days: val.days,
        sum1: val.sum1,
        sum2: val.sum1 - val.sum1 * 0.15
      };

      this.workers.push(newWorker);
      this.totalSum = this.workers.reduce((acc, worker) => acc + worker.sum1, 0); 
      this.totalSum2 = this.workers.reduce((acc, worker) => acc + worker.sum2, 0); 

    },
    removeWorker(id) {
      this.workers = this.workers.filter(worker => worker.id !== id);
      this.totalSum = this.workers.reduce((acc, worker) => acc + worker.sum1, 0);
      this.totalSum2 = this.workers.reduce((acc, worker) => acc + worker.sum2, 0); 
    }
  }
};
</script>

<style scoped>

</style>
