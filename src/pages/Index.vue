<template>
  <q-page class="flex flex-center">

    <Loop />


  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

import Loop from '../components/main-components/Loop.vue'

export default defineComponent({
  name: 'PageIndex',
  components: {

    Loop

  }
})
</script>
