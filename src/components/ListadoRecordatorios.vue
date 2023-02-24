<template>
  <div>
    <q-list bordered style="width: 350px">
      <q-item v-for="(item, key) in datos" :key="key" clickable v-ripple>
        <q-item-section avatar>
          <q-avatar color="teal" text-color="white" icon="task" />
        </q-item-section>

        <q-item-section>{{ item.nombre }}</q-item-section>
        <q-item-section>{{ item.fecha }}</q-item-section>
      </q-item>
    </q-list>
  </div>
</template>

<script setup>
//leer datos del localstorage y ordenarlos por fecha
import { ref, onMounted } from "vue";
import { useQuasar } from "quasar";

const $q = useQuasar();
const datos = ref([]);

//onMounted(() => {
//  let arreglo = JSON.parse($q.localStorage.getItem("datos"));
//console.log(arreglo._value);
//  if (arreglo != null) {
//    datos.value = arreglo._value;
//    datos.value.sort((a, b) => a.fecha - b.fecha);
//  }
//});
</script>
