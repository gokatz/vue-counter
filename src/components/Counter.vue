<template>
  <div>
    <button class="inc" @click="decrement"> - </button>
    Count: {{this.count}}
    <button class="dec" @click="increment"> + </button>
    <div v-if="isMax" class="alert"> Max Value Reached! </div>
  </div>
</template>

<script lang="js">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  count = 0;
  maxValue = 10;

  decrement() {
    this.count > 0 && this.count--;
  }

  increment() {
    this.count < this.maxValue && this.count++;
  }

  get isMax() {
    return this.count >= this.maxValue;
  }
}
</script>
