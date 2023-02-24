<template>
  <q-page>
    <!--
    <h6>Listado de Recordatorios</h6>
    -->

    <q-page-sticky position="top-right" :offset="[55, 10]">
      <!--
      <q-btn to="/nuevo" fab icon="add" color="secondary" />
      -->
    </q-page-sticky>
    <div class="row justify-center q-mt-sm">
      <listado-recordatorios />
    </div>
  </q-page>
</template>

<script setup>
import ListadoRecordatorios from "src/components/ListadoRecordatorios.vue";
</script>
