<script setup>
import {ref} from 'vue';

let count = ref(0);

</script>

<template>
  <div>

    <h1>{{ count }}</h1>
    <button @click="count++">Incrementar</button>

  </div>
</template>

<style scoped>

</style>
