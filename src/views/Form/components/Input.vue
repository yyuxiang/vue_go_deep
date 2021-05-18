<template>
    <input
        v-bind="$attrs"
        :value="value"
        :type="type"
        @input="input"
        @blur="blur"
    >
</template>

<script>
export default {
    inheritAttrs: false, // 关闭特性继承 避免根组件继承特性
    props: {
        // 输入框的值
        value: {
            type: String,
            default: '',
        },
        // 输入框类型
        type: {
            type: String,
            default: 'text'
        }
    },
    data() {
        return {

        }
    },
    components: {

    },
    computed: {

    },
    methods: {
        input(e) {
            this.$emit(e.target.value)
        },
        blur(e) {
            console.log(e.target.value,' 99')
            this.$parent.$emit('blur',e.target.value)
        }
    },
}
</script>

<style scoped lang="scss">
.input_container {
    padding: 10px 0;
}
</style>
