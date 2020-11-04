<template>
  <q-card square flat>
    <q-img :src="data.flag" />

    <q-card-section class="q-pt-none">
      <div class="text-h6">Nome</div>
      <div class="text-body1">{{ data.name }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">Nome nativo</div>
      <div class="text-body1">{{ data.nativeName }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">Capital</div>
      <div class="text-body1">{{ data.capital }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">Região</div>
      <div class="text-body1">{{ data.region }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">Sub região</div>
      <div class="text-body1">{{ data.subregion }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">População</div>
      <div class="text-body1">{{ data.population }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">Área</div>
      <div class="text-body1">{{ data.area }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">Fuso horário</div>
      <div class="text-body1">{{ data.timezones }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <div class="text-h6">Link da bandeira</div>
      <div class="text-body1">
        <a target="_black" :href="data.flag">{{ data.flag }}</a>
      </div>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  props: ["data"],
}
</script>

<style>
</style>