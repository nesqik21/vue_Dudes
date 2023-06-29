<template>
    <div>
<form  @input="valueChanged" @keydown.enter="formSubmitted" class="add-new">
    <input ref="firstInput" v-model="newDude.name"  type="text" />
    <input v-model="newDude.subtitle" type="text" /> 
</form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                newDude:{name:'',subtitle:''}
            }
        },
        methods: {
            formSubmitted() {
                this.$emit('add-dude',this.newDude)
                this.newDude = {name:'',subtitle:''}
                this.valueChanged();
                this.$refs.firstInput.focus()
            },
            valueChanged(e){
                window.eventBus.emit('new-preview',this.newDude)
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>