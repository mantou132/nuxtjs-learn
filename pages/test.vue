<script setup lang="ts">
import DySpace from 'duoyun-ui/vue/DySpace.vue'
import DyButton from 'duoyun-ui/vue/DyButton.vue'
import DyCard from 'duoyun-ui/vue/DyCard.vue'
import DyColorPicker from 'duoyun-ui/vue/DyColorPicker.vue'
import DyParagraph from 'duoyun-ui/vue/DyParagraph.vue'
import type { HexColor } from 'duoyun-ui/lib/color'

const colorElement = ref<InstanceType<typeof DyColorPicker>>();
const cardActions = ref([{ text: 'Action1', handle: console.log }, { text: 'Action2', handle: console.log }, { text: 'Action3', handle: console.log }, { text: 'Action4', handle: console.log }]);
const cardHeader = ref('This header');
const color = ref<HexColor>('#f0f');

const clickHandle = () => {
  cardActions.value = cardActions.value.reverse()
  cardHeader.value = [...cardHeader.value].reverse().join('')
}

const onChange = (e: CustomEvent<HexColor>) => {
  color.value = e.detail
}

</script>

<template>
  <DyParagraph>
    <DySpace>
      <DyButton @click="() => colorElement?.showPicker()">Open Color Picker</DyButton>
      <DyColorPicker ref=colorElement :value="color" alpha @change="onChange"></DyColorPicker>
      <dy-color-picker :value="color" alpha @change="onChange"></dy-color-picker>
    </DySpace>
  </DyParagraph>

  <DySpace>
    <DyCard @click="clickHandle" class="card" avatar="https://api.dicebear.com/5.x/bottts-neutral/svg"
      preview="https://picsum.photos/400/300" :header="cardHeader" :detail="`CE`" :actions="cardActions">Fugiat do laboris
      ad
      officia in anim qui mollit
      nulla reprehenderit pariatur anim sunt.</DyCard>
    <dy-card @click="clickHandle" class="card" avatar="https://api.dicebear.com/5.x/bottts-neutral/svg"
      preview="https://picsum.photos/400/300" .header="cardHeader" .detail="`CE`" .actions="cardActions">Fugiat do laboris
      ad
      officia in anim qui mollit
      nulla reprehenderit pariatur anim sunt.</dy-card>
  </DySpace>
</template>

<style scoped>
.card {
  width: 300px;
}
</style>