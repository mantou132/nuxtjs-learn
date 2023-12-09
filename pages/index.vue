<script setup lang="ts">
import AppAlert from '../components/AppAlert.vue';
const alert = ref<InstanceType<typeof AppAlert>>()
const counter = ref(0)

const clickHandle = () => {
  alert.value?.hi('hi')
  counter.value++
}

const onUpdate = (value: string) => {
  console.log(value);
}
</script>
<template>
  <div @click="clickHandle">
    <AppAlert ref="alert" :counter="counter" @update="onUpdate" >
      This is an auto-imported component
    </AppAlert>
  </div>
</template>