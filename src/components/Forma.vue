<template>
  <form @submit.prevent="handleSubmit">
    <div class="mb-3">
      <label for="fio" class="form-label">ФИО сотрудника</label>
      <input type="text" class="form-control" id="fio" v-model="fio" placeholder="Введите ФИО">
    </div>
    <div class="mb-3">
      <label for="date" class="form-label">Дата выдачи зарплаты</label>
      <input type="date" class="form-control" id="date" v-model="date">
    </div>
    <div class="mb-3">
      <label for="days" class="form-label">Количество отработанных дней</label>
      <input type="number" class="form-control" id="days" v-model="days">
    </div>
    <div class="mb-3">
      <label for="salary" class="form-label">Размер заработной платы сотрудника</label>
      <input type="number" class="form-control" id="salary" v-model="salary">
    </div>
    <button type="submit" class="btn btn-outline-primary">Добавить</button>
  </form>
</template>

<script>
export default {
  props: {
    addWorker: {
      type: Function,
      required: true
    }
  },
  data() {
    return {
      fio: '',
      date: '',
      days: 0,
      salary: 0
    };
  },
  methods: {
    handleSubmit() {
      this.addWorker({
        fio: this.fio,
        date: this.date,
        days: this.days,
        sum1: this.salary
      });
    }
  }
};
</script>

<style scoped>

</style>
