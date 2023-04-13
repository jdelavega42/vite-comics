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
    </header>
</template>

<style lang="scss" scoped>
header {
    display: flex;
    justify-content: space-between;
    padding: 2rem 10rem;


    ul {
        display: flex;
        gap: 1rem;
        
        li {
            position: relative;
            padding: 0 .5rem;
            align-self: center;
            
            a::after {
                content: '';
                position: absolute;
                left: 0;
                bottom: -50px;
                width: 100%;
                border-bottom: 10px solid blue;
                display: none;
            }
            &:hover a::after{
                display: block;
            }
        }
    }
}
</style>