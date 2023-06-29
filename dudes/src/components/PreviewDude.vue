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
        props:['dude']
    }
</script>

<style lang="scss" scoped>

</style>