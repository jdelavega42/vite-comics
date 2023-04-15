<script>
export default {
    name: "AppFooter",
}
</script>

<template>
    <footer>
        <div class="container">
            <div class="button">Sign Up Now!!</div>
            <div class="items">
                <span>Follow Us</span>
                <ul class="icons">
                    <li>
                        <a href=""><img src="../assets/img/footer-facebook.png" alt=""></a>
                    </li>
                    <li>
                        <a href=""><img src="../assets/img/footer-twitter.png" alt=""></a>
                    </li>
                    <li>
                        <a href=""><img src="../assets/img/footer-youtube.png" alt=""></a>
                    </li>
                    <li>
                        <a href=""><img src="../assets/img/footer-pinterest.png" alt=""></a>
                    </li>
                    <li>
                        <a href=""><img src="../assets/img/footer-periscope.png" alt=""></a>
                    </li>
                </ul>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

footer {
    background-color: #303030;
    color: white;
    padding: 1rem;
    position: relative;
    z-index: 2;
    .container{
        width: $default-width;
            @include spacing(0 auto, 0 1rem 1rem);
            @include flex(row, space-between, center, 0);

            .button {
                padding: .5rem;
                border: 1px solid $primary-color;
            }
            .items {
                @include flex(row, flex-start, center, 1rem);
                span {
                    color: $primary-color
                }
                .icons {
                    @include flex(row, flex-start, center, 1rem);
                    
                }
            }
    }
}

</style>