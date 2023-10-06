<script setup>
import { reactive } from 'vue';
import Progress from './components/Progress.vue'

let courses = reactive([{
  title: "Javascript",
  done: true
}, {
  title: "React",
  done: false
}, {
  title: "Vue",
  done: true
},
]);

let newCourse = {done: false}

function addCourse() {
  courses.push(newCourse);
  newCourse = {done: false};
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

    <Progress :courses="courses" />

  </div>
</template>

<style scoped></style>
