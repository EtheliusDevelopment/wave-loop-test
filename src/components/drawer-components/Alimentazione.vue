<template>
  <h5 class="title-filters">Alimentazione</h5>
  <div class="inputs-field">
    <q-checkbox
      label="Elettrica (11)"
      id="checkbox"
      v-model="val"
      @click="passEvent(product)"
    />
    <q-checkbox
      label="Metano (1)"
      id="checkbox"
      v-model="val2"
      @click="passEvent(product)"
    />
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const val = ref(false);
    const val2 = ref(false);

    return{
      val,
      val2
    }

  },
}
</script>
