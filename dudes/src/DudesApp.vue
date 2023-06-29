<template>
<div>
    <ul>
    <li v-for="(dude,index) in characters" :key="index">
        <Dude :name="dude.name" :subtitle="dude.subtitle"/>
    </li>
</ul>

<create-form-dude @new-preview="newDude = $event" @add-dude="characters.push($event);emptyNewDude()" />
<preview-dude :dude="newDude"/>

</div>
</template> 

<script>
import Dude from './components/Dude.vue'; 
import CreateFormDude from './components/CreateFormDude.vue'; 
import PreviewDude from './components/PreviewDude.vue'; 

export default {
    components: {
        Dude,
        CreateFormDude,
        PreviewDude
    },
    data() {
        return {
            newDude:{name:'',subtitle:''},
            characters: [
                {name:'Homer Simpson',subtitle:'He is from The Simpsons series, where he is funny dude.'},
                {name:'Cartman', subtitle:'He is from The Southpark series, he is small fat dude.'},
                {name:'Rick and Morty',subtitle:'They are from the Rick and Morthy series, I dont know them'}]
        }
    },
    methods: {
        emptyNewDude() {
            this.newDude={name:'',subtitle:''}
        }
    },
}
</script>

<style>

</style>