<template>
  <div>
    <SubTitle :text="text" style="font-size: 18px; padding: 0px" />
    <input
      v-model="inputValue"
      type="text"
      placeholder="Text"
      class="input"
      :style="{ height: ySize }"
      @input="updateValue"
    />
  </div>
</template>

<script setup>
import SubTitle from '../ListPage/MainContent/atom/SubTitle.vue'
import { ref,watch } from 'vue'

const props = defineProps({
  text: String,
  ySize: String
})

const inputValue = ref('')

const emit = defineEmits()

const updateValue = () => {
  emit('update:modelValue', inputValue.value)
}

</script>

<style lang="scss" scoped>
.input {
  width: 360px;
  height: 80px;
  border: 1px solid #bebebe;
  border-radius: 4px;
  padding: 0px 0px 0px 10px;
}
input::placeholder {
  color: #303494;
}
</style>
