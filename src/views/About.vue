<template xmlns:checked="http://www.w3.org/1999/xhtml">
  <div class="about">
    <H3>Liste des tâches</H3><br><br>
    <div class="columns">
      <div class="column">
        Description de la tâche
      <br>  <input type="text" v-model="nouvelledescription"><br><br>
        <ul>
          <li v-for="tache in taches" :key="tache.description">
            {{ tache.description }}
          </li>
        </ul>
      </div>
      <div class="column is-success">
        Debut de la tâche
        <br>  <input type="text" v-model="nouveaudebut"><br><br>
        <ul>
          <li v-for="tache in taches" :key="tache.description">
            {{ tache.debut }}
          </li>
        </ul>
      </div>
      <div class="column">
        Fin de la tâche
        <br>  <input type="text" v-model="nouvellefin"><br><br>
        <ul>
          <li v-for="tache in taches" :key="tache.description">
            {{ tache.fin }}
          </li>
        </ul>
      </div>
      <div class="column">
        Effectuée
        <br>  <label class="checkbox">
        <input type="checkbox" v-model="nouveleffect">
      </label><br><br>
        <ul>
          <li v-for="tache in taches" :key="tache.description">
            <label class="checkbox">
              <input :checked="tache.effect == true" type="checkbox">
            </label>
          </li>
        </ul>
      </div>
      <div class="column">
        Actions
        <br>  <button @click="ajouter">Ajouter la tâche</button><br><br>
        <ul>
          <li v-for="(tache, index) in taches" :key="tache.description">
            <button @click="modifier">Modifier</button>
            <button @click="supprimer(index)">Supprimer</button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>

// import firebase from './firebaseInit';
// const db = firebase.firestore();

export default { // el: '#about',
  data() {
    return {
      taches: [
        {
          description: 'Cuisiner', debut: '11h', fin: '12h', effect: false,
        },
        {
          description: 'Faire le menage', debut: '10h', fin: '13h', effect: false,
        },
        {
          description: 'Faire les devoirs', debut: '25 dec.', fin: '31dec.', effect: true,
        },
      ],
      nouvelledescription: '',
      nouveaudebut: '',
      nouvellefin: '',
      nouveleffect: false,
    };
  },
  methods: {
    ajouter() {
      this.taches.push(
        {
          description: this.nouvelledescription,
          debut: this.nouveaudebut,
          fin: this.nouvellefin,
          effect: this.nouveleffect,
        },
        this.nouvelledescription = '',
        this.nouveaudebut = '',
        this.nouvellefin = '',
        this.nouveleffect = false,
      );
    },
    modifier() {
    },
    supprimer(index) {
      this.taches.slice(index, 1);
      // vue.Delete(Object, index);
      // this.taches.$remove(index, 1);
    },
  },
};
</script>
