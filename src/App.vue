<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div id="app">
    <h1 :class="{ red: isRed }" :style="{ fontSize: fontSize + 'px' }">
      Welcome to My Vue App
    </h1>
    <input type="text" v-model="inputValue" @input="handleInput" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      isRed: false,
      fontSize: 24,
      inputValue: '',
    };
  },
  methods: {
    handleInput(event) {
      this.inputValue = event.target.value;
      this.isRed = this.inputValue.length > 5;
      this.fontSize = this.inputValue.length * 2;
    },
  },
};
</script>

<style scoped>
.red {
  color: red;
}
</style>