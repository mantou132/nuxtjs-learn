<script setup lang="ts">
const span = ref<HTMLSpanElement>()
const props = defineProps<{
  counter?: number,
  elements?: string[]
}>();

const emit = defineEmits<{
  change: []
  update: [value: string]
}>()

defineExpose({
  hi: console.log.bind(console),
})

watch(() => props.counter, () => {
  span.value?.focus();
  console.log("Counter value changed");
});

</script>
<template>
  <span ref="span">
    Counter {{ counter }}
    <slot />
  </span>
</template>