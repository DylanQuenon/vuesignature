<template>
  <div id="app">
    <SaisieSignature @input-changed="updateFicheData" />
    <FicheSignature :ficheData="ficheData" />
  </div>
</template>

<script>
import SaisieSignature from './components/SaisieSignature.vue'
import FicheSignature from './components/FicheSignature.vue'

export default {
  name: 'App',
  components: {
    SaisieSignature,
    FicheSignature,
  },
  data() {
    return {
      ficheData: {
        name: '',
        firstname:'',
        mail: '',
        tel: '',
        selectedCitation: '',
      }
    };
  },
  methods: {
    updateFicheData(data) {
      this.ficheData = data;
    }
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  width: 100%;
  justify-content: center;
}
</style>
