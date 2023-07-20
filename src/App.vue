<template>
  <h1>VueJS</h1>
  <Car :power="power" :increasePower="increasePower" @decreasePower="decreasePower"/>
</template>

<script>
import { ref } from "vue";

import Car from "./components/Car.vue";

export default {
  components: {
    Car,
  },
  setup(props) {
    let power = ref(30);

    const increasePower = () => power.value++;
    const decreasePower = () => power.value--;

    return {
      power,
      increasePower,
      decreasePower,
    };
  },
};
</script>

<style></style>
