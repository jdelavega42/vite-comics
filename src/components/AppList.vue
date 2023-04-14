<script>
export default {
    name: "AppList",
    data() {
        return {
            lists: [
                { name: "DC Comics", links: ["Characters", "Comics", "Movies", "TV", "Games", "Videos", "News"] },
                { name: "Shop", links: ["Shop DC", "Shop DC Collectibles"]},
                { name: "DC", links: ["Terms Of Use", "Privaci policy (New)", "Ad Choices", "Advertising", "Jobs", "Subscriptions", "Talent Workshops", "CPSC Certificates", "Ratings", "Shop Help", "Contact Us"] },
                { name: "Sites", links: ["DC", "MAD Magazine", "DC Kids", "DC Universe", "DC Power Visa"] }
            ]
        }
    }
}
</script>

<template>
    <main>
        <div class="list">
            <ul>
                <li  class="title" v-for="list in lists">
                    <p>{{ list.name }}</p>
                    <ul>
                        <li class="subtitle" v-for="link in list.links">
                            <a href="">{{ link }}</a>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
        <!-- <div>
            <img src="../assets/img/dc-logo-bg.png" alt="">
        </div> -->
    </main>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;
    main {
        background-image: url(../assets/img/footer-bg.jpg);
        color: white;
        & .list {
            height: 40rem;
            width: $default-width;
            @include spacing(0 auto, 1rem);
            & ul {
                width: 50%;
                @include flex(column wrap, flex-start, flex-start, .5rem );
                & .title {
                    width: calc(100% / 3);
                    font-weight: bolder;

                    & ul {
                        & .subtitle {
                            font-weight: lighter;
                        }
                    }
                }
            }
        }
        
    }
</style>