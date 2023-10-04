<script setup>
import { ref, reactive } from 'vue';

let count = ref(0);

let courses = reactive([{
  title: "Javascript"
}, {
  title: "React"
}, {
  title: "Vue"
},
]);

let newCourse = {}

function increment() {
  count.value++;
}

function addCourse() {
  courses.push(newCourse);
  newCourse = {};
}

</script>

<template>
  <div>

    <h1>Lista de Cursos</h1>
    <ul>
      <li v-for="course in courses" :key="course.title">
        {{ course.title }}

      </li>
    </ul>

    <br>

    <input v-model="newCourse.title" type="text">
    <button @click="addCourse">Adicionar</button>

  </div>
</template>

<style scoped></style>
