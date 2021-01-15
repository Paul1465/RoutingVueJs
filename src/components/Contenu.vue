<template>
  <div class="container mt-5">

    <h1> {{ titre }} </h1>

      <div class="btn btn-outline-primary mr-2" v-on:click="component = 'texte1'">Onglet 1</div>
      <div class="btn btn-outline-primary mr-2" v-on:click="component = 'texte2'">Onglet 2</div>

      <div class="onglets card mb-5">
        <component class="p-5" v-bind:is="component"></component>
      </div>
      
      <modale v-bind:revele="revele" v-bind:toggleModale="toggleModale"></modale>
      <div v-on:click="toggleModale" class="btn btn-success">Ouvre la modale</div>

  </div>
</template>

<script>

    import Texte1 from './Texte1'
    import Texte2 from './Texte2'
    import Modale from './Modale'

    export default {
        name: 'Contenu',
        data(){
          return {
            myArr : [
              {titre: 'Inception', date: 2010},
              {titre: 'Avatar', date: 2009},
              {titre: 'Seven', date: 1995}
            ],
            txt: 'Hello World',
            titre: 'Je suis le Titre',
            togle1: true,
            toggle2: false,
            component: 'texte1',
            revele: false
          }
        },
        methods: {
          toggleOng1: function(){
            this.toggle1 = true
            this.toggle2 = false
          },
          toggleOng2: function(){
            this.toggle1 = false
            this.toggle2 = true
          },
          toggleModale: function(){
          this.revele = !this.revele
          }
        },
        components: {
          'texte1': Texte1,
          'texte2': Texte2,
          'modale': Modale
        }
    }
</script>

<style>
h1 {
  margin-top: 100px!important;
}
.onglets {
  height: 300px;
}
.overlay {
  background: rgba(0,0,0,0.5);
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  left:0;
}
.modale {
  background: #f1f1f1;
  color: #333;
  padding:50px;
  position:fixed;
  bottom:10%;
}
.btn-modale{
  position: absolute;
  top:10px;
  right:10px;
}
</style>