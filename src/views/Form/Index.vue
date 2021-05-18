<template>
    <div class="container">
        <Form :model="model" :rules="rules">
            <FormItem label="账号" prop="userName">
                <Input
                    v-model="model.userName"
                    placeholder="请输入账号"
                />
            </FormItem>
            <FormItem label="密码" prop="password">
                <Input
                    v-model="model.password"
                    type="password"
                    placeholder="请输入密码"
                />
            </FormItem>
            <FormItem>
                <button>登录</button>
            </FormItem>
        </Form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            model: {
                userName: '',
                password: '',
            },
            rules: {
                userName: [
                    {
                        require: true,
                        message: '请输入账号'
                    }
                ],
                password: [
                    {
                        require: true,
                        message: '请输入密码'
                    }
                ]
            }
        }
    },
    components: {
        Form: () => import('./components/Form'),
        FormItem: () => import('./components/FormItem'),
        Input: () => import('./components/Input')
    },
    computed: {

    },
    methods: {

    },
}
</script>

<style scoped lang="scss">
</style>
