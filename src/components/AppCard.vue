<script>
export default {
    name:"AppCard",
    props: {
        thumb: String,
        price: String,
        series: String,
        type: String,
    },
}
</script>
    
<template>
    <div class="card">
        <div>
            <img :src="thumb" alt="">
        </div>
        <p>{{ series }}</p>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;

    .card {
        width: calc(100% / 6);
        height: 250px;
        padding: .5rem;
        
        div {
            height: 90%;
            width: 100%;

            img {
                height: 100%;
                width: 100%;
                object-fit: cover;
                object-position: top;
            }
        }

        p {
            padding-top: .2rem;
            height: 10%;
            font-size: .75rem;
        }
    }
</style>