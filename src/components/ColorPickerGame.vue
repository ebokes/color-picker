<template>
  <div class="container">
    <h1>Color Picker Game</h1>

    <div class="prompt">
      {{ message }}
    </div>
    <div class="button-container">
      <button
        :style="{ backgroundColor: color }"
        v-for="color in colors"
        :key="color"
        @click="matchColor(color)"
      >
        {{ color }}
      </button>
    </div>
  </div>
</template>

<script setup>
import { useColorPicker } from "../composables/color-picker";

const { colors, message, matchColor } = useColorPicker();
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
}

.button-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 5px;
}

.prompt {
  text-align: center;
  margin-bottom: 10px;
}

button {
  color: #fff;
  padding: 3px;
  width: 100%;
  border-radius: 6px;
  cursor: pointer;
  font-size: 16px;
}

span {
  width: 200px;
  height: 200px;
}
</style>
