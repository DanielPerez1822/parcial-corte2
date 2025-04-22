<!-- filepath: src/components/CustomerForm.vue -->
<template>
      <div>
        <label for="name">Nombre:</label>
        <input type="text" id="name" v-model="customer.name" required />
      </div>
      <div>
        <label for="contact">Contacto:</label>
        <input type="text" id="contact" v-model="customer.contact" required />
      </div>
      <button type="submit">Enviar</button>
  </template>
  
  <script>
  export default {
    name: "CustomerForm",
    data() {
      return {
        customer: {
          name: "",
          contact: "",
        },
      };
    },
    methods: {
      submitForm() {
        this.$emit("submit", this.customer);
      },
    },
  };
  </script>
  
  <style scoped>
  form {
    display: flex;
    flex-direction: column;
    gap: 10px;
    background-color: #f9f9f9; 
    padding: 20px;
    border: 1px solid #cccccc; 
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); 
  }

  label {
    font-weight: bold;
    color: #0056b3; 
  }

  input {
    padding: 8px;
    border: 1px solid #999999; 
    border-radius: 4px;
    font-size: 14px;
    background-color: #d9d9d9; 
  }

  button {
    margin-top: 10px;
    padding: 10px;
    background-color: #0078d4; 
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
    transition: background-color 0.3s;
  }

  button:hover {
    background-color: #0056b3; 
  }

  .summary p strong {
    color: #0056b3;
  }
  </style>