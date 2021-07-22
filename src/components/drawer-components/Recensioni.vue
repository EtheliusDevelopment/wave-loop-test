<template>
  <h5 class="title-filters">Recensioni</h5>
  <div class="inputs-field">
    <div class="review-check">
      <q-checkbox id="checkbox" v-model="val" @click="passEvent(product)" />
      <div class="stars">
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_border" color="primary" />
      </div>

      <p class="note q-ml-sm">(3)</p>
    </div>
    <div class="review-check">
      <q-checkbox id="checkbox" v-model="val" @click="passEvent(product)" />
      <div class="stars">
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_border" color="primary" />
      </div>

      <p class="note q-ml-sm">(14)</p>
    </div>

    <div class="review-check">
      <q-checkbox id="checkbox" v-model="val" @click="passEvent(product)" />
      <div class="stars">
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_border" color="primary" />
      </div>

      <p class="note q-ml-sm">(5)</p>
    </div>

    <div class="review-check">
      <q-checkbox id="checkbox" v-model="val" @click="passEvent(product)" />
      <div class="stars">
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_rate" color="primary" />
        <q-icon class="icon-star" name="star_border" color="primary" />
      </div>

      <p class="note q-ml-sm">(1)</p>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const val = ref(false);
    const val2 = ref(false);
    const val3 = ref(false);
    const val4 = ref(false);

    return {
      val,
      val2,
      val3,
      val4,
    };
  },
};
</script>

<style lang="scss" scoped>
.stars {
  display: flex;
  align-items: center;
}

i.notranslate.material-icons.q-icon.icon-star {
  margin: 0 0.03vw !important;
}

.review-check {
  display: flex;
}

.note {
  opacity: 0.4;
  display: flex;
  align-items: center;
  margin: 0;
  margin-left: 0.1rem;
}
</style>
