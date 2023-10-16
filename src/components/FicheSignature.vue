<template>
    <div class="card_signature">
      <div class="fiche">
        <p class="name">
        
          <strong>{{ ficheData.name }}</strong>
       
          {{ ficheData.firstname }}
        </p>
        <p class="mail">{{ ficheData.mail }}</p>
        <p class="telephone">{{ ficheData.tel }}</p>
        <div class="bar"></div>
        <p class="citations">
         
      <em v-if="ficheData.selectedCitation.text !== ''">&ldquo;{{ ficheData.selectedCitation.text }}&rdquo;</em><br>

          <strong>{{ ficheData.selectedCitation.author }}</strong> 
        </p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'FicheSignature',
    props: {
      ficheData: Object // Vous devez recevoir les données de votre composant parent
    },
    data() {
      return {};
    },
  };
  </script>
  
  <style scoped>
  .card_signature {
    width: 50%;
    min-height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .fiche {
    width: 85%;
    min-height: 200px;
    background-color: rgb(208, 208, 206);
  }
  
  .bar {
    width: 85%;
    margin: 0 auto;
    height: 2px;
    background-color: rgb(92, 92, 92);
    margin-top: 15px;
    margin-bottom: 15px;
  }
  
  p {
    text-align: start;
    margin: 15px 7.5% 0 7.5%;
    width: auto;
  }
  .mail{
    text-decoration: underline;
  }
 
  </style>
  