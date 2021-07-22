<template>
  <h5 class="title-filters">Potenza Nominale <span class="kw">Kw</span></h5>
  <div class="inputs-field">
    <q-checkbox
      label="19.5 (1)"
      id="checkbox"
      v-model="val"
      @click="passEvent(product)"
    />
    <q-checkbox
      label="24 (5)"
      id="checkbox"
      v-model="val2"
      @click="passEvent(product)"
    />
       <q-checkbox
      label="25 (2)"
      id="checkbox"
      v-model="val3"
      @click="passEvent(product)"
    />
    <q-checkbox
      label="da 30 a 34 (2)"
      id="checkbox"
      v-model="val4"
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
    const val3 = ref(false);
    const val4 = ref(false);

    return{
      val,
      val2,
      val3,
      val4
    }

  },
}
</script>

