<template>
    <div>
      <h2>Child Component</h2>
      <button @click="emitData">Send Data to Parent</button>
      <slot :slotData="slotData"></slot>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        slotData: 'This is data from child'
      };
    },
    methods: {
      emitData() {
        this.$emit('data-updated', this.slotData);
      }
    }
  };
  </script>