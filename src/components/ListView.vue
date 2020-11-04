<template>
  <q-item clickable v-ripple :to="'/' + data.alpha2Code">
    <q-item-section avatar>
      <q-avatar>
        <q-img :src="data.flag" spinner-color="white" />
      </q-avatar>
    </q-item-section>
    <q-item-section>
      <q-item-label>{{ data.name }}</q-item-label>
      <q-item-label caption>{{ data.nativeName }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  props: ["data"],
}
</script>

<style>
</style>