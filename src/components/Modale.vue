<template>
    <div class="bloc-modale" v-if="revele">
        <div v-on:click="toggleModale" class="overlay"></div>
            <div class="modale card">
                <div v-on:click="toggleModale" class="btn-modale btn btn-danger">X</div>
                    <h2>Le contenu de la modale</h2>
                </div>
            </div>
</template>
<script>

export default {
    name: 'Modale',
    props: ['revele', 'toggleModale']
}

</script>
<style>

.bloc-modale{
    position: fixed;
    top:0;
    bottom:0;
    left:0;
    right:0;
    width:100%;
    height:100%;
    display:flex;
    justify-content:center;
    align-items: center; 
}

</style>