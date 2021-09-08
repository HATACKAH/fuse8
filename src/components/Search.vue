<template>
    <div class="filter">
        <p class="filter__title">Filter</p>
        <input
            type="search"
            class="filter__input"
            :value="value"
            @keyup="onKeyUp"
        >
    </div>
</template>

<script>
export default {
    name: 'Search',
    props: {
		value: String,
	},
    methods: {
        onKeyUp(e) {
            this.$emit('input', e.target.value);
        },
    },
};
</script>

<style scoped>
.filter {
    display: flex;
    margin: 60px 0px 60px 25px;
}
.filter__title {
    font-size: 16px;
    line-height: 24px;
    font-weight: bold;
    margin-right: 25px;
    letter-spacing: -0.3px;
}
.filter__input {
    width: 418px;
    height: 50px;

    border: 1px solid #d8d8d8;
    border-radius: 25px;
}
@media (max-width: 700px) {
    .filter{
        margin: 60px 10px 60px 10px;
    }
}
</style>
