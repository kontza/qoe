<template>
  <h1>{{ msg }}</h1>

  <div class="row">
    <div class="col-2 offset-2">
      <q-btn @click="count++" color="primary">count is: {{ count }}</q-btn>
    </div>
    <div class="col-2 offset-4">
      <q-btn @click="count++" color="secondary">count is: {{ count }}</q-btn>
    </div>
  </div>

  <div class="row">
    <div class="col offset-4">
      <DatePicker />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import DatePicker from './DatePicker.vue'

defineProps({
  msg: String
})

const count = ref(0)
</script>
