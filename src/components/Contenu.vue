<template>
    <div class="container mt-5">
        <h1>Notre premier formulaire </h1>
        <form>
            <div class="form-group">
                <label for="prenom">Ton prénom</label>
                <input v-on:input="toggleResult" v-model="formData.prenom" type="text" id="prenom" class="form-control">
            </div>

            <div class="form-group">
                <label for="txt">Ton texte</label>
                <textarea v-on:input="toggleResult" v-model="formData.txt" class="form-control" id="txt"></textarea>
            </div>

            <h3>Select Box</h3>

            <select v-on:input="toggleResult" v-model="formData.select">
                <option v-bind:key="index" v-for="(pays, index) in formData.listePays">{{ pays }}</option>
            </select>

            <h3 class="mt-3">CheckBoxs</h3>

            <div class="form-check">
                <input v-on:input="toggleResult" v-model="formData.checkFruits" value="fraise" id="fraise" type="checkbox" class="form-check-input">
                <label for="fraise">Fraise</label>
            </div>

            <div class="form-check">
                <input v-on:input="toggleResult" v-model="formData.checkFruits" value="pomme" id="pomme" type="checkbox" class="form-check-input">
                <label for="pomme">Pomme</label>
            </div>

            <div class="form-check">
                <input v-on:input="toggleResult" v-model="formData.checkFruits"  value="cerise" id="cerise" type="checkbox" class="form-check-input">
                <label for="cerise">Cerise</label>
            </div>

            <button v-on:click.prevent="envoiForm" class="btn btn-primary mt-3 mb-3">Envoyez les données</button>
        </form>
        <div v-if="infoSubmit">
            <h2>Résultats</h2>
                    <div class="card p-3">
                        <p>Prénom : {{ formData.prenom }} </p>
                        <p style="white-space: pre">Texte : {{ formData.txt }} </p>

                        <p>Résultats checkbox</p>
                        <ul>
                            <li v-bind:key="index" v-for="(fruit, index) in formData.checkFruits"> {{ fruit }}</li>
                        </ul>
                        <p>Choix du select : {{ formData.select }}</p>
                    </div>
        </div>
    </div>
</template>

<script>    
    export default {
        name: 'Contenu',
        data(){
            return {
                formData: { //pr mieux organiser les données
                    prenom: '',
                    txt: '',
                    checkFruits: [],
                    select: '',
                    listePays: ['Russie', 'Japon', 'Suede', 'France', 'Angleterre']
                },
                infoSubmit: false // on le cache au depart
            }
        },
        methods: {
           envoiForm: function(){
               this.infoSubmit = true;
           },
           toggleResult: function(){
               this.infoSubmit = false;
           }
        }
    }
</script>

<style>
    h1 {
        margin-top: 100px!important;
    }
    .onglets{
        height: 300px;
    }
</style>