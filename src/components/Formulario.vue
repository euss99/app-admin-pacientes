<script setup>
import { reactive } from "vue";
import Alerta from "./Alerta.vue";

const emit = defineEmits([
  "update:nombre-mascota",
  "update:nombre-propietario",
  "update:email",
  "update:alta",
  "update:sintomas",
  "guardar-paciente",
]);

const props = defineProps({
  nombreMascota: {
    type: String,
    requiered: true,
  },
  nombrePropietario: {
    type: String,
    requiered: true,
  },
  email: {
    type: String,
    requiered: true,
  },
  alta: {
    type: String,
    requiered: true,
  },
  sintomas: {
    type: String,
    requiered: true,
  },
});

const alerta = reactive({
  tipo: "",
  mensaje: "",
});

const validar = () => {
  const pacienteValidacion = Object.values(props).includes("");

  if (pacienteValidacion) {
    alerta.mensaje = "Todos los campos son obligatorios";
    alerta.tipo = "error";
    return;
  }

  emit("guardar-paciente");

  alerta.mensaje = "Enviado correctamente";
  alerta.tipo = "exito";
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

    <Alerta v-if="alerta.mensaje" :alerta="alerta" />

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
          :value="nombreMascota"
          @input="$emit('update:nombre-mascota', $event.target.value)"
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
          :value="nombrePropietario"
          @input="$emit('update:nombre-propietario', $event.target.value)"
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
          :value="email"
          @input="$emit('update:email', $event.target.value)"
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
          :value="alta"
          @input="$emit('update:alta', $event.target.value)"
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
          :value="sintomas"
          @input="$emit('update:sintomas', $event.target.value)"
        />
      </div>

      <input
        type="submit"
        class="bg-indigo-600 w-full p-3 text-white uppercase rounded-md font-bold hover:bg-indigo-700 cursor-pointer transition-colors"
        value="Registrar paciente"
      />
    </form>
  </div>
</template>
