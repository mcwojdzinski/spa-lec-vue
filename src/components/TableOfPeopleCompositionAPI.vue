<script setup>
import {ref, computed} from 'vue';

const firstName = ref('');
const lastName = ref('');
const peopleArr = ref([]);
const numberOfPeople = computed(() => peopleArr.value.length)
const addPerson = () => {
  peopleArr.value.push({firstName: firstName.value, lastName: lastName.value});

  firstName.value = '';
  lastName.value = '';
}


</script>

<template>
  <div class="table-wrapper">

    <form @submit.prevent="addPerson" class="form">
      <label for="firstName">
        First name:
        <input v-model="firstName" placeholder="Enter first name" type="text" id="firstName"/>
      </label>
      <label for="lastname">
        Last name:
        <input v-model="lastName" placeholder="Enter last name" type="text" id="lastName"/>
      </label>
      <button type="submit">Add person</button>
    </form>

    <table class="table">
      <thead>
      <td>Nr.</td>
      <td>Imię</td>
      <td>Nazwisko</td>
      </thead>
      <tbody>
      <tr v-for="(person, index) in peopleArr" :key="index">
        <td>{{ index }}</td>
        <td>{{ person.firstName }}</td>
        <td>{{ person.lastName}}</td>
      </tr>
      </tbody>
    </table>
  </div>
  <p class="total">Total people count: {{ numberOfPeople }}</p>
</template>

<style scoped>
.table-wrapper {
  display: flex;
  flex-direction: row;
  column-gap: 30px;
  align-items: flex-start;
}
.form {
  display: flex;
  flex-direction: column;
  row-gap: 15px;

}
.table {
  width: 100%;
  border-collapse: collapse;
}
.table td {
border: 1px solid brown;
}

.table thead {
  background-color: chocolate;
}

.total {
  text-align: right;
}
</style>