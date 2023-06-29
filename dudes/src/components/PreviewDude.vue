<template>
    <div>
        <p class="preview">
            {{dude.name }}
        </p>
        <p class="preview">
            {{dude.subtitle }}
        </p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                dude:{name:'',subtitle:''}
            }
        },
        created () {
            window.eventBus.on('new-preview',event => {
                this.dude = event
            });
        },
        }
    
</script>

<style lang="scss" scoped>

</style>