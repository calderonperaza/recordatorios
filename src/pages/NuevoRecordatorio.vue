<template>
  <q-page>
    <h5 class="row justify-center q-ma-md">Agregar Recordatorio</h5>
    <div class="row justify-center q-ma-md">
      <q-input
        v-model="recordatorio"
        class="col-3"
        square
        outlined
        label="Recordatorio"
      />
    </div>
    <div class="row justify-center q-ma-md">
      <q-input
        v-model="fecha"
        class="col-3"
        square
        outlined
        type="date"
        hint="Fecha"
      />
    </div>
    <div class="row justify-center q-mt-xl">
      <q-btn to="/" color="white" text-color="black" label="cancelar" />
      <q-btn @click="agregar" color="primary" label="Agregar" />
    </div>
  </q-page>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { date, useQuasar } from "quasar";
import { useRouter } from "vue-router";

const recordatorio = ref("");
const fecha = ref(date.formatDate(Date.now(), "YYYY-MM-DD"));
const $q = useQuasar();
const router = useRouter();
const datos = ref([]);

function agregar() {
  datos.value.push({
    nombre: recordatorio.value,
    fecha: fecha.value,
    hecho: false,
  });
  $q.localStorage.set("datos", JSON.stringify(datos));

  $q.notify({
    message: "Recordatorio Agregado",
    color: "green",
    icon: "save",
  });
  router.push("/");
}

onMounted(() => {
  let arreglo = JSON.parse($q.localStorage.getItem("datos"));
  //console.log(arreglo._value);
  if (arreglo != null) datos.value = arreglo._value;
});
</script>
