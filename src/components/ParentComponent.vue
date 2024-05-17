<template>
    <div>
      <h1>Parent Component</h1>
      <ChildComponent @data-updated="updateDataFromChild">
        <template v-slot:default="slotProps">
          <p>Data from slot: {{ slotProps.slotData }}</p>
        </template>
      </ChildComponent>
      <p>Data from child: {{ dataFromChild }}</p>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  
  export default {
    components: {
      ChildComponent
    },
    data() {
      return {
        dataFromChild: ''
      };
    },
    methods: {
      updateDataFromChild(data) {
        this.dataFromChild = data;
      }
    }
  };
  </script>