<template>
    <div>
<form  @input="valueChanged" @keydown.enter="formSubmitted" class="add-new">
    <input ref="firstInput" v-model="newName"  type="text" />
    <input v-model="subtitle" type="text" /> 
</form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                newName:'',
                subtitle:''
            }
        },
        methods: {
            formSubmitted() {
                this.$emit('add-dude',{name:this.newName,subtitle:this.subtitle})
                this.newName=''
                this.subtitle=''
                this.$refs.firstInput.focus()
            },
            valueChanged(e){
                this.$emit('new-preview',{name:this.newName,subtitle:this.subtitle})
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>