<template>
  <BaseLayout>
    <div class="gestion-reservas-page">
      <h1>Gestión de Reservas</h1>
      <div class="card">
        <select_table 
          :tables="tables" 
          @update:table="updateSelectedTable" 
        />
        <select_date 
          @update:datetime="updateSelectedDateTime" 
        />
        <CustomerForm 
          @submit="handleFormSubmit" 
        />
        <div v-if="reservationSummary" class="summary">
          <h2>Resumen de la Reserva</h2>
          <p><strong>Mesa:</strong> {{ reservationSummary.table }}</p>
          <p><strong>Fecha y Hora:</strong> {{ reservationSummary.datetime }}</p>
          <p><strong>Cliente:</strong> {{ reservationSummary.customer.name }}</p>
          <p><strong>Contacto:</strong> {{ reservationSummary.customer.contact }}</p>
        </div>
      </div>
    </div>
  </BaseLayout>
</template>

<script setup lang="ts">
import BaseLayout from '@/components/BaseLayout.vue';
import select_table from '@/components/select_table.vue';
import select_date from '@/components/select_date.vue';
import CustomerForm from '@/components/form.vue';

const tables = [
  { id: 1, capacity: 4 },
  { id: 2, capacity: 6 },
  { id: 3, capacity: 2 },
];

let selectedTable = null;
let selectedDateTime = '';
let reservationSummary = null;

const updateSelectedTable = (tableId: number) => {
  selectedTable = tableId;
};

const updateSelectedDateTime = (datetime: string) => {
  selectedDateTime = datetime;
};

const handleFormSubmit = (customer: { name: string; contact: string }) => {
  reservationSummary = {
    table: selectedTable,
    datetime: selectedDateTime,
    customer,
  };
};
</script>

<style scoped>
.gestion-reservas-page {
  font-family: Arial, sans-serif;
  margin: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.card {
  background-color: #f9f9f9; /* Light gray background */
  border: 1px solid #cccccc; /* Light gray border */
  border-radius: 8px;
  padding: 20px;
  width: 100%;
  max-width: 600px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Subtle shadow */
}

.card h1 {
  color: #0056b3; /* Darker blue */
  margin-bottom: 20px;
  text-align: center;
}

.summary {
  margin-top: 20px;
  padding: 10px;
  border: 1px solid #0056b3; /* Darker blue border */
  border-radius: 5px;
  background-color: #e6f2ff; /* Light blue background */
}

</style>
