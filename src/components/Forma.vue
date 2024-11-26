<template>
    <form>
      <div class="mb-3">
        <label for="fio" class="form-label">ФИО сотрудника</label>
        <input  type="text" class="form-control" id="fio" placeholder="Введите ФИО">
      </div>
      <div class="mb-3">
        <label for="date" class="form-label">Дата выдачи зарплаты</label>
        <input type="date" class="form-control" id="date">
      </div>
      <div class="mb-3">
        <label for="days" class="form-label">Количество отработанных дней </label>
        <input type="number" class="form-control" id="days">
      </div>
      <div class="mb-3">
        <label for="" class="form-label">Размер заработной платы сотрудника</label>
        <input type="number" class="form-control" id="days">
      </div>
      <button type="button" class="btn btn-outline-primary">Добавить</button>
    </form>

</template>

<script>
export default {

}
</script>

<style scoped>

</style>