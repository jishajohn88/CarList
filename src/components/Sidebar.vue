<!-- eslint-disable vue/multi-word-component-names -->

<template>
    <aside>

    </aside>
</template>
<script>

export default {

}
</script>
<style scoped>
 aside{
    display: flex;
    flex-direction: column;
    background-color: bisque;
    color: black;
    width: 300px;
    overflow: hidden;
    min-height: 100vh;
    padding: 1rem;
    @media (max-width: 768px){
        position: relative;
        z-index: -1;
          margin: 0 15px 0 0;
    }
 }
</style>
