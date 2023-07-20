<template>
    <h2>Coche - Options</h2>
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
    <button @click="increasePower(10)">Aumentar</button>
    <button @click="decreasePower">Dismunuir</button>
  </template>
  
  <script>
  export default {
    data() {
      return {
        brand: 'audi',
        model: 'A4',
        colors: ['Azul', 'Rojo'],
        price: 38000,
        powers: [60, 80, 120, 160, 200, 280, 300, 390, 540, 500],
        mensaje: {
          title: 'Hola mundo',
          text: 'Adiós',
        },
        actualPower: 50,
      }
    },
    methods: {
      increasePower (newPower) {
        this.actualPower += newPower; 
      },
      decreasePower () {
        this.actualPower--;
      }
    }
  }
  </script>
  
  <style></style>