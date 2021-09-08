<template>
    <article class="homeCard">
        <a :href="`/details/${cardInfo.id}`">
            <div class="homeCard__image">
                <div class="homeCard__label" :class="className">
                    <span v-if="isSupportAvailable"
                        >Restaurant & Support available</span
                    >
                    <span v-else>Independent living</span>
                </div>
            </div>
            <div class="homeCard__info">
                <p class="homeCard__title" v-text="cardInfo.title" />
                <p class="homeCard__address" v-text="cardInfo.address" />
                <p class="homeCard__price">
                    New Properties for Sale from
                    <b> &#163;{{ cardInfo.price }} </b>
                </p>
                <p class="homeCard__additional">Shared Ownership Available</p>
            </div>
        </a>
    </article>
</template>

<script>
export default {
    name: 'HomeCard',
    props: {
        cardInfo: {
            type: Object,
            required: true,
        },
    },
    computed: {
        isSupportAvailable() {
            return this.cardInfo.type == 'SupportAvailable';
        },
        className() {
            return this.isSupportAvailable ? 'orange' : 'blue';
        },
    },
};
</script>

<style scoped>
* {
    color: #363636;
    text-decoration: none;
}
.homeCard__label.orange {
    background: #ec6608;
}
.homeCard__label.blue {
    background: #006f79;
}
.homeCard__label {
    width: auto;
    height: 30px;
    margin-left: auto;
    margin-top: auto;
}
.homeCard__label > span {
    font-weight: bold;
    font-size: 12px;
    line-height: 16px;
    padding: 8px 10px 5px 10px;
    color: #FFFFFF;
}
.homeCard {
    width: 379px;
    height: 381px;
    border: 1px solid #d8d8d8;
    margin: 39px 21px;
}

.homeCard__image {
    width: 100%;
    height: 200px;
    background: url('https://via.placeholder.com/379x200/774886/774886?text=title')
        no-repeat;
    display: flex;
}

.homeCard__info {
    margin-left: 20px;
}

.homeCard__title {
    font-weight: 700;
    font-size: 20px;
    line-height: 27px;
}
.homeCard__address,
.homeCard__price {
    font-size: 16px;
    line-height: 22px;
}
@media (max-width: 700px) {
    .homeCard__image {
        width: 330px;
    }
    .homeCard__info {
        margin-left: 15px;
    }
}
</style>
