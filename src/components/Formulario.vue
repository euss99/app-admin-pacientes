<script setup>
import { reactive } from "vue";
import Alerta from "./Alerta.vue";

const alerta = reactive({});

const paciente = reactive({
  nombreMascota: "",
  nombrePaciente: "",
  email: "",
  alta: "",
  sintomas: "",
});

const validar = () => {
  const pacienteValidacion = Object.values(paciente).includes("");

  if (pacienteValidacion) {
    console.log("Si estan vacios...");
    return;
  }

  console.log("Enviar...");
};
</script>

<template>
  <div class="md:w-1/2">
    <h2 class="font-black text-3xl text-center">Seguimiento de pacientes</h2>

    <p class="text-lg mt-5 text-center mb-10">
      Añade pacientes y
      <span class="text-indigo-600 font-bold">adminístralos</span>
    </p>

    <form
      class="bg-white shadow-md rounded-lg py-10 px-5 mb-10"
      @submit.prevent="validar"
    >
      <div class="mb-5">
        <label for="mascota" class="block text-gray-700 uppercase font-bold"
          >Nombre mascota</label
        >
        <input
          id="mascota"
          type="text"
          class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
          placeholder="Nombre de la mascota"
          v-model="paciente.nombreMascota"
        />
      </div>
      <div class="mb-5">
        <label for="propietario" class="block text-gray-700 uppercase font-bold"
          >Nombre propietario</label
        >
        <input
          id="propietario"
          type="text"
          class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
          placeholder="Nombre del propietario"
          v-model="paciente.nombrePaciente"
        />
      </div>
      <div class="mb-5">
        <label for="email" class="block text-gray-700 uppercase font-bold"
          >Email</label
        >
        <input
          id="email"
          type="text"
          class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
          placeholder="Email del propietario"
          v-model="paciente.email"
        />
      </div>
      <div class="mb-5">
        <label for="alta" class="block text-gray-700 uppercase font-bold"
          >Fecha de alta</label
        >
        <input
          id="alta"
          type="date"
          class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
          v-model="paciente.alta"
        />
      </div>
      <div class="mb-5">
        <label for="sintomas" class="block text-gray-700 uppercase font-bold"
          >Síntomas</label
        >
        <textarea
          id="sintomas"
          class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
          placeholder="Describe los sintomas"
          v-model="paciente.sintomas"
        />
      </div>

      <input
        type="submit"
        class="bg-indigo-600 w-full p-3 text-white uppercase font-bold hover:bg-indigo-700 cursor-pointer transition-colors"
        value="Registrar paciente"
      />
    </form>
  </div>
</template>
