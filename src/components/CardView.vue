<template>
  <div>
    <q-card square>
      <q-img :src="data.flag" spinner-color="white" />
      <q-card-section>
        <div class="text-h5">{{ data.name }}</div>
        <div class="text-body1">{{ data.nativeName }}</div>
      </q-card-section>
      <q-card-actions>
        <q-btn
          rounded
          color="primary"
          class="full-width"
          label="detalhes"
          :to="'/' + data.alpha2Code"
        />
      </q-card-actions>
    </q-card>
  </div>
</template>

<script>
export default {
  props: ["data"],
}
</script>

<style>
</style>