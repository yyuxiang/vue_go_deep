<template>
    <form>
        <slot />
    </form>
</template>

<script>
export default {
    props: {
        model: {
            type: Object,
            default: () => ({})
        },
        rules: {
            type: Object,
            default: () => ({})
        },
    },
    provide() {
        return {
            form: this,  
        }
    },
    components: {

    },
    computed: {

    },
    methods: {

    },
}
</script>

<style scoped lang="scss">
</style>
