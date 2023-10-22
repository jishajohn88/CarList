<!-- eslint-disable vue/multi-word-component-names -->
<!-- eslint-disable space-before-blocks -->
<template>
    <header>
        <h3>{{title}}</h3>
    </header>
</template>

<script>
export default {
  data () {
    return {
      title: 'Listing Feed'
    }
  }
}
</script>
<style>
    header{
        background-color: aquamarine;
        padding: 10px;
        height: 50px;
        text-align: center;
        color: black;
        width: 100%;
        position: absolute;
    }
</style>
