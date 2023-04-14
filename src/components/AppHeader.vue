<script>
export default {
    name: 'AppHeader',
    data() {
        return {
            links: [
                {text: "characters", url: "#", current: false},
                {text: "comics", url: "#", current: true},
                {text: "movies", url: "#", current: false},
                {text: "tv", url: "#", current: false},
                {text: "games", url: "#", current: false},
                {text: "collectibles", url: "#", current: false},
                {text: "videos", url: "#", current: false},
                {text: "fans", url: "#", current: false},
                {text: "news", url: "#", current: false},
                {text: "shop", url: "#", current: false}
            ]
        }
    }
}
</script>

<template>
    <header>
        <section>
            <div class="logo">
                <a href="#">
                    <img src="../assets/img/dc-logo.png" alt="">
                </a>
            </div>
            <ul>
                <li v-for="link in links" :class="{'active': link.current}">
                    <a :href="link.url">{{ link.text }}</a>
                </li>
            </ul>
        </section>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

section {
    width: $default-width;
    @include spacing(0 auto, 1rem);
    @include flex(auto, space-between, auto, auto);
    
    ul {
        @include flex(auto, auto, auto, 1rem);
        
        li {
            position: relative;
            padding: 0 .5rem;
            align-self: center;
        }
    }
}
</style>