<template>
  <q-page>
    <q-page-sticky position="top-right" :offset="[55, 10]">
      <q-btn to="/nuevo" fab icon="add" color="secondary" />
    </q-page-sticky>
    <div class="row justify-center q-mt-sm">
      <img
        alt="Quasar logo"
        src="~assets/quasar-logo-vertical.svg"
        style="width: 200px; height: 200px"
      />
    </div>
  </q-page>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { useQuasar } from "quasar";

const $q = useQuasar();
const datos = ref([]);

onMounted(() => {
  let arreglo = JSON.parse($q.localStorage.getItem("datos"));
  //console.log(arreglo._value);
  if (arreglo != null) {
    datos.value = arreglo._value;
    datos.value.sort((a, b) => a.fecha - b.fecha);
  }
});
</script>
