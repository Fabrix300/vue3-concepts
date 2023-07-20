<template>
  <h2>Coche - Composition</h2>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ model }}</p>
  <p>Color:
    <!-- <span v-for="(color, index) in colors" :key="index">
      {{ index }}: {{ color }} - 
    </span> -->
  </p>
  <ul>
    <li v-for="(color, index) in colors" :key="index">
      {{ index }}: {{ color }}
    </li>
  </ul>
  <p>Precio: ${{ price }}</p>
  <p>Potencias:</p>
  <ul>
    <!-- <li v-for="(power, index) in powers" :key="index">
      <template v-if="power < 300">
        {{ power }}
      </template>
    </li> -->
    <template v-for="(power, index) in powers" :key="index">
      <li v-if="power < 280">
        Urbana: {{ power }}
      </li>
      <li v-else-if="power === 280">
        Híbrido: {{ power }}
      </li>
      <li v-else>
        Carrera: {{ power }}
      </li>

      <li v-if="power === 500">
        Súper: {{ power }}
      </li>
    </template>
  </ul>
  <p>{{ mensaje.title }} - {{ mensaje.text }}</p>
  <p>Potencia actual: {{ actualPower }}</p>
  <button @click="increasePower">Aumentar</button>
  <button @click="decreasePower(10)">Dismunuir</button>
</template>

<script>
import { ref } from 'vue';

export default {
  setup(props) {
    const brand = 'audi';
    const model = 'A4';
    const colors = ['Azul', 'Rojo'];
    const price = 38000;
    const powers = [60, 80, 120, 160, 200, 280, 300, 390, 540, 500];
    const mensaje = {
      title: 'Hola mundo',
      text: 'Adiós',
    };
    let actualPower = ref(50);

    const increasePower = () => actualPower.value++;
    const decreasePower = (newPower) => actualPower.value -= newPower;

    return {
      brand,
      model,
      colors,
      price,
      powers,
      mensaje,
      actualPower,
      increasePower,
      decreasePower,
    }
  }
}
</script>

<style></style>