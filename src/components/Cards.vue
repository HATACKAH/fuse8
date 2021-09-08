<template>
    <section class="container">
        <Search v-model="searchQuery" />
        <div class="wrapper">
            <HomeCard
                v-for="card in pageResults"
                :key="card.id"
                :cardInfo="card"
            />
        </div>
    </section>
</template>

<script>
import HomeCard from './HomeCard.vue';
import Search from './Search.vue';

export default {
    components: { HomeCard, Search },
    name: 'Cards',
    data: () => ({
        searchQuery: '',
        results: [],
    }),
    async mounted() {
        this.results = await fetch(
            'https://603e38c548171b0017b2ecf7.mockapi.io/homes'
        ).then((x) => x.json());
    },
    computed: {
        filteredResults() {
            if (this.searchQuery.length < 3) return this.results;

            return this.results.filter((homeCard) =>
                homeCard.title.includes(this.searchQuery)
            );
        },
        pageResults() {
            return this.filteredResults.slice(0, 6);
        },
    },
};
</script>

<style scoped>
.wrapper {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    margin: 0 auto;
}
@media (max-width: 1715px) {
    .wrapper {
        min-width: 900px;
    }
}
@media (max-width: 1200px) {
    .wrapper {
        min-width: 600px;
    }
}
@media (max-width: 700px) {
    .wrapper {
        justify-content: center;
        min-width: 330px;
    }
}
</style>
