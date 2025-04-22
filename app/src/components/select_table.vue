<template>
    <div>
      <label for="table">Selecciona una mesa:</label>
      <select id="table" v-model="selectedTable" @change="emitTable">
        <option v-for="table in tables" :key="table.id" :value="table.id">
          Mesa {{ table.id }} - {{ table.capacity }} personas
        </option>
      </select>
    </div>
  </template>
  
  <script>
  export default {
    name: "TableSelector",
    props: {
      tables: {
        type: Array,
        required: true,
      },
    },
    data() {
      return {
        selectedTable: null,
      };
    },
    methods: {
      emitTable() {
        this.$emit("update:table", this.selectedTable);
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

  select {
    padding: 8px;
    border: 1px solid #cccccc;
    border-radius: 4px;
    font-size: 14px;
    background-color: #f0f0f0;
  }
  </style>