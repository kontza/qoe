<template>
  <h1>{{ msg }}</h1>

  <div class="row">
    <div class="col-2 offset-2">
      <q-btn @click="incrementCount" color="primary">count is: {{ count }}</q-btn>
    </div>
    <div class="col-4">
      Date in parent: {{selectedDate}}
    </div>
    <div class="col-2">
      <q-btn @click="incrementCount" color="secondary">count is: {{ count }}</q-btn>
    </div>
  </div>

  <div class="row">
    <div class="col offset-4">
      <DatePicker :selectedDate="selectedDate" @dateSelected="onDateSelected" />
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
var selectedDate = ref('2021/12/24')

function incrementCount() {
  count.value++
}

function onDateSelected(newDate) {
  selectedDate.value = newDate
}
</script>
