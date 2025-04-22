<template>
    <div>
      <label for="reservation-datetime">Selecciona fecha y hora:</label>
      <input
        type="datetime-local"
        id="reservation-datetime"
        v-model="selectedDateTime"
        @change="emitDateTime"
      />
    </div>
  </template>
  
  <script>
  export default {
    name: "DateTimePicker",
    data() {
      return {
        selectedDateTime: "",
      };
    },
    methods: {
      emitDateTime() {
        this.$emit("update:datetime", this.selectedDateTime);
      },
    },
  };
  </script>
  
  <style scoped>
  label {
    font-weight: bold;
    margin-right: 8px;
    color: #0056b3;
  }

  input[type="datetime-local"] {
    padding: 8px;
    border: 1px solid #999999;  
    border-radius: 4px;
    font-size: 14px;
    background-color: #f0f0f0;  
  }
  </style>