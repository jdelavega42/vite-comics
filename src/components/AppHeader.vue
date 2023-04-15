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
            ],
            active: 0
        }
    },
    methods: {
        getActiveIndex(currentIndex){
            this.links.forEach(element => {
                element.current = false;
            });
            this.links[currentIndex].current = true;
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
                <li v-for="(link, index) in links" :key="index" :class="{'active': link.current}">
                    <a @click="getActiveIndex(index)" :href="link.url">{{ link.text }}</a>
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
    @include spacing(0 auto, 1rem 1rem 0);
    @include flex(auto, space-between, auto, auto);
    
    ul {
        @include flex(row wrap, flex-start, stretch, 1rem);
        
        li {
            height: 100%;
            display: flex;
            align-items: center;
            position: relative;

            a {
                padding: 0 .5rem;

            }
        }

    }

}
.active {
    background: linear-gradient(180deg, white 0 90%, $primary-color 95%);
}

li:hover ::after {
    content: '';
        @include p-absolute(calc(100% - 5px), 0, 0);
        width: 100%;
        border-bottom: 5px solid $primary-color;
        
}
</style>