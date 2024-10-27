<script setup>
import TableOfPeople from "@/components/TableOfPeopleCompositionAPI.vue";
import TableOfPeopleOptionsAPI from "@/components/TableOfPeopleOptionsAPI.vue";
</script>

<template>
  <div>

    <h1>Component with <b>Composition API</b></h1>
    <TableOfPeople />
  </div>
  <div>
    <h1>Component with <b>Option API</b></h1>
    <TableOfPeopleOptionsAPI />
  </div>
</template>

<style scoped>
</style>
