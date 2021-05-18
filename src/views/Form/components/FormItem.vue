<template>
    <div class="container">
        <span class="error_color" v-if="isRequire">*</span>
        <!-- 标签名 -->
        <label>{{label}}</label>
        <slot />
        <!-- 错误信息 -->
        <span
            class="error_color"
            v-show="error"
        >{{error}}</span>
    </div>
</template>

<script>
export default {
    props: {
        // 标签名
        label: {
            type: String,
            default: ''
        },
        // 标签名
        prop: {
            type: String,
            default: ''
        }
    },
    inject: ['form'],
    data() {
        return {
            error: '', // 错误信息
        }
    },
    components: {

    },
    computed: {
        isRequire() {
            return this.prop?this.form.rules[this.prop][0].require:''
        }
    },
    mounted() {
        // this.error = this.form.rules[this.prop][0]
        this.$on('blur', (val) => {
            if(!val) {
                this.error = this.form.rules[this.prop][0].message
            }
        })
    },
    methods: {

    },
}
</script>

<style scoped lang="scss">
.error_color {
    color: red;
}
</style>
