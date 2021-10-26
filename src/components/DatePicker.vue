<template>
  <div class="q-pa-md" style="max-width: 300px">
    <div>Date in component: {{selectedDate}}</div>
    <q-input filled v-model="selectedDate" mask="date" :rules="['date']">
      <template v-slot:append>
        <q-icon name="event" class="cursor-pointer">
          <q-popup-proxy ref="qDateProxy" transition-show="scale" transition-hide="scale">
            <q-date v-model="selectedDate" today-btn>
              <div class="row items-center justify-end">
                <q-btn v-close-popup label="Close" color="primary" flat />
              </div>
            </q-date>
          </q-popup-proxy>
        </q-icon>
      </template>
    </q-input>
  </div>
</template>
<script>
import { ref } from 'vue'

export default {
  props: ['selectedDate'],
  watch: {
    selectedDate(newValue, oldValue) {
      this.$emit('dateSelected', newValue)
    }
  }
}
</script>