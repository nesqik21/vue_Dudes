<template>
<div>
    <ul>
    <li v-for="(dude,index) in characters" :key="index">
        <Dude :name="dude.name" :subtitle="dude.subtitle"/>
    </li>
</ul>

<form @submit.prevent="characters.push(newDude )" class="add-new">
    <input v-model="newDude" type="text" /> 
</form>

<p class="preview">
    {{newDude }}
</p>
</div>
</template>

<script>
import Dude from './components/Dude.vue';

export default {
    components: {
        Dude,
    },
    data() {
        return {
            newDude:'',
            characters: [
                {name:'Homer Simpson',subtitle:'He is from The Simpsons series, where he is funny dude.'},
                {name:'Cartman', subtitle:'He is from The Southpark series, he is small fat dude.'},
                {name:'Rick and Morty',subtitle:'They are from the Rick and Morthy series, I dont know them'}]
        }
    },
}
</script>

<style>

</style>