<template>
  <h2>Coche - Composition</h2>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ model }}</p>
  <p>Potencia: {{ power }}</p>
  <button @click="increasePower">Aumentar</button>
  <button @click="decreasePower">Disminuir</button>
</template>

<script>
export default {
  props: {
    power: {
      type: Number,
      default: 60,
    },
    increasePower: Function,
  },
  emits: ["decreasePower"],
  setup(props, context) {
    const brand = "audi";
    const model = "A4";

    const decreasePower = () => context.emit("decreasePower");

    return {
      brand,
      model,
      decreasePower,
    };
  },
};
</script>

<style></style>
