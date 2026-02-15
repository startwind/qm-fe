<template>
  <table>
    <thead>
      <tr>
        <th></th>
        <th v-for="countryMints, country in mints">
          <span v-for="mint in countryMints" style="margin-right: 20px;">
            {{ mint }} // {{ country }} 
          </span> 
        </th>
      </tr>
      <tr v-for="coin in coins" :key="coin">
        <td>{{ coin }}</td>
        <td v-for="mint in mints" :key="mint">{{ coinData[coin][mint] }}</td>
      </tr>
    </thead>


  </table>
</template>
 
<script setup>

const mints = {
  Deutschland: ['Berlin', 'München', 'Stuttgart', 'Hamburg'],
  Frankreich: ['Paris']
}

// const mints = ['Berlin', 'München', 'Stuttgart', 'Hamburg'];
const coins = ['1 Euro', '2 Euro', '50 Cent', '20 Cent'];

const coinData = {
  '1 Euro': { Berlin: 3, München: 3, Stuttgart: 2, Hamburg: 1 },
  '2 Euro': { Berlin: 80, München: 90, Stuttgart: 110, Hamburg: 95 },
  '50 Cent': { Berlin: 200, München: 250, Stuttgart: 220, Hamburg: 210 },
  '20 Cent': { Berlin: 300, München: 350, Stuttgart: 320, Hamburg: 310 }
}

console.log(coinData['1 Euro']['Berlin']); // Output: 3

</script>