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
        <div class="container">
            <div class="list">
                <div class="column">
                    <div class="section">
                        <p  class="title">{{ lists[0].name }}</p>
                        <ul>
                            <li v-for="link in lists[0].links">
                                <a class="subtitle" href="#">{{ link }}</a>
                            </li>
                        </ul>
                    </div>
                    <div class="section">
                        <p  class="title">{{ lists[1].name }}</p>
                        <ul>
                            <li v-for="link in lists[1].links">
                                <a class="subtitle" href="#">{{ link }}</a>
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="column">
                    <div class="section">
                        <p  class="title">{{ lists[2].name }}</p>
                        <ul>
                            <li v-for="link in lists[2].links">
                                <a class="subtitle" href="#">{{ link }}</a>
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="column">
                    <div class="section">
                        <p  class="title">{{ lists[3].name }}</p>
                        <ul>
                            <li v-for="link in lists[3].links">
                                <a class="subtitle" href="#">{{ link }}</a>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="logo">
                <img src="../assets/img/dc-logo-bg.png" alt="">
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;
    main {
        background-image: url(../assets/img/footer-bg.jpg);
        background-repeat: no-repeat;
        color: white;

        .container {
            width: $default-width;
            @include flex(row, space-between, stretch);
            @include spacing(0 auto, 1rem);
            .list {
                width: 40%;
                @include flex(row wrap, flex-start, stretch);
                .column {
                    width: calc(100% / 3);
                    .section {
                        margin-bottom: .5rem;
                        .title {
                           font-size: 1.25rem;
                           font-weight: bold; 
                        }
                        .subtitle{
                            font-size: .75rem;
                        }
                    }
                }
            }
            .logo {
                width: 400px;
                position: relative;
                img {
                    @include p-absolute(50%, 50%, 1);
                    transform: translate(50%, -50%);
                }
            }
        }
    }
</style>