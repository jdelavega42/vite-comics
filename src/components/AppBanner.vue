<script>
export default {
    name: "AppBanner",
    data() {
        return {
            cards: [
                {image: "buy-comics-digital-comics.png", text: "Digital Comics"},
                {image: "buy-comics-merchandise.png", text: "DC Merchandise"},
                {image: "buy-comics-subscriptions.png", text: "Subscription"},
                {image: "buy-comics-shop-locator.png", text: "Comic Shop Locator"},
                {image: "buy-dc-power-visa.svg", text: "DC Power Visa"}
            ]
        }
    },
    methods: {
        getImage(element){
            return new URL(`../assets/img/${element.image}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <main>
        <ul>
            <li v-for="card in cards">
                <div class="box">
                    <img :src="getImage(card)">
                </div>
                <a href="">{{ card.text }}</a>
            </li>
        </ul>
    </main>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

    main {
        position: relative;
        z-index: 2;
        background-color: $primary-color;
        ul {
            width: $default-width;
            @include spacing(0 auto, 1rem);
            @include flex(auto, space-around, center, auto);
            color: white;

            li {
                @include flex(auto, auto, center, 1rem);
                .box{
                    @include spacing(.5rem 0, 0);
                    width: 3rem;
                    img{
                        height: 3rem;
                        max-width: 3rem;
                    }
                }
            }
        }
    }
</style>