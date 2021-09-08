<template>
    <main class="container">
        <h1>Our Latest Developments</h1>
        <Cards />
        <Button />
    </main>
</template>

<script>
import Button from './Button.vue';
import Cards from './Cards.vue';
export default {
    components: {
        Cards,
        Button,
    },
};
</script>

<style scoped>
h1 {
    font-size: 36px;
    line-height: 49px;
    text-align: center;
    font-weight: 700;
    color: #45852d;
}
.container {
    max-width: 1300px;
    height: 100%;
    margin: 0 auto;
}
</style>
