<template>
    <div id="app">
        <Form />
    </div>
</template>

<script>

export default {
  name: 'App',
  components: {
      Form: () => import('@/views/Form/Index')
  }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
