<template>
  <h5 class="title-filters">Tipologia</h5>
  <div class="inputs-field">
    <q-checkbox
      label="A Condensazione (3)"
      id="checkbox"
      v-model="val"
      @click="passEvent(product)"
    />
    <q-checkbox
      label="Camera Aperta (7)"
      id="checkbox"
      v-model="val2"
      @click="passEvent(product)"
    />
      <q-checkbox
      label="Camera Stagna (4)"
      id="checkbox"
      v-model="val3"
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


    return{
      val,
      val2,
      val3
    }

  },
}
</script>



