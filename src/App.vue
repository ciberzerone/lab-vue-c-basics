<script lang="ts" setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

import { ref } from 'vue';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
const isVisible = ref(true);

const toggleVisibility = () => {
  isVisible.value = !isVisible.value;
};
const getResult = () => 5 * 3;
const items = ref(['Elemento 1', 'Elemento 2', 'Elemento 3']);

const isGreen = ref(false);

const toggleColor = () => {
  isGreen.value = !isGreen.value;
};

</script>


<template>
  <Navbar />
  <header>
 
    <div>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
      </li>
    </ul>
  </div>

  </header>
 

  <main>
    <div>
    <p v-if="isVisible">Este mensaje solo se muestra si isVisible es true.</p>
    <button @click="toggleVisibility">Cambiar Visibilidad</button>
  </div>
  <div>
    Resultado de 2 + 2 es: {{ 2 + 2 }}
    <br />
    Resultado de la función es: {{ getResult() }}
  </div>


  <div :class="{ 'bg-green': isGreen }" class="box">
    Haz clic en el botón para cambiar el color de fondo
  </div>
  <button @click="toggleColor">Cambiar Color</button>


  </main>





 







  <router-view />
  

  <Footer />



</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

.box {
  width: 200px;
  height: 200px;
  background-color: lightgray;
}

.bg-green {
  background-color: green;
}
</style>
