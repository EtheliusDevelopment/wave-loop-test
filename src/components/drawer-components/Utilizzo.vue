<template>
  <h5 class="title-filters">Utilizzo</h5>
  <div class="inputs-field">
    <q-checkbox
      label="Esterno (4)"
      id="checkbox"
      v-model="val"
      @click="passEvent(product)"
    />
    <q-checkbox
      label="Interno / Iterno (2)"
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




