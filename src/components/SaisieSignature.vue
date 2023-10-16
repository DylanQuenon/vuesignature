<template>
    <div class="inputList">
      <div class="box">
        <input type="text" name="nom" id="nom" placeholder="Nom" v-model="name" @input="updateFiche">
        <input type="text" name="prenom" id="prenom" placeholder="Prénom" v-model="firstname" @input="updateFiche">
        <input type="email" name="email" id="email" placeholder="Votre adresse mail" v-model="mail" @input="updateFiche">
        <input type="tel" name="tel" id="tel" placeholder="Votre numéro de téléphone" v-model="tel" @input="updateFiche">
  
        <select v-model="selectedCitation" @change="updateFiche">
          <option value="" disabled selected>Choisissez une citation</option>
          <option v-for="(citation, index) in options" :key="index" :value="citation">
            {{ citation.text }} - <strong>{{ citation.author }}</strong>
          </option>
        </select>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'SaisieSignature',
    data() {
      return {
        selectedCitation: '',
        options: [
        { text: "La vie est la fleur dont l'amour est le miel.", author: "Victor Hugo" },
        { text: "La simplicité est la sophistication suprême.", author: "Leonardo da Vinci" },
        { text: "L'avenir appartient à ceux qui croient en la beauté de leurs rêves.", author: "Eleanor Roosevelt" },
        { text: "Le bonheur est un parfum que l'on ne peut répandre sur autrui sans en faire rejaillir quelques gouttes sur soi-même.", author: "Ralph Waldo Emerson" },
        { text: "La vie est vraiment simple, mais nous insistons à la compliquer.", author: "Confucius" },
        { text: "L'homme est la seule créature qui refuse d'être ce qu'il est.", author: "Albert Camus" },
        { text: "L'éducation est l'arme la plus puissante que l'on puisse utiliser pour changer le monde.", author: "Nelson Mandela" },
        { text: "La seule façon de faire du bon travail est d'aimer ce que vous faites.", author: "Steve Jobs" },
        { text: "La persévérance est le secret de la réussite.", author: "Victor Hugo" },
        { text: "La liberté, c'est la possibilité de dire aux autres ce qu'ils ne veulent pas entendre.", author: "George Orwell" }
        ],
        name: "",
        firstname: "",
        mail: "",
        tel: "",
      };
    },
    methods: {
    updateFiche() {
      // Émettez un événement pour transmettre les données au composant parent
      this.$emit('input-changed', {
        name: this.name,
        firstname: this.firstname,
        mail: this.mail,
        tel: this.tel,
        selectedCitation: this.selectedCitation,
      });
    }
  }
  };
  </script>
  
  <style scoped>
  .box {
    width: 100%;
    min-height: calc(100vh - 150px);
    background-color: gray;
    display: flex;
    flex-direction: column;
  }
  
  .box input {
    margin: 20px;
    padding: 10px;
    width: 80%;
    &:focus {
      outline: none;
    }
  }
  
  .box select {
    width: 400px;
    height: 30px;
    border: none;
    outline: none;
    margin: 20px;
  }
  
  input::placeholder,
  select {
    font-weight: bold;
    color: black;
  }
  
  option {
    font-weight: normal;
  }
  
  .inputList {
    width: 60%;
  }
  </style>
  