<script>
export default {
    props: {
        comic: Object,
    }
}
</script>

<template>
    <div class="card">
        <img :src="comic.thumb" :alt="comic.series">
        <span>{{ comic.price }}<br>{{ comic.type }}</span>
        {{ comic.series }}
    </div>
</template>

<style lang="scss" scoped>
.card {
    flex-basis: calc(100% / 6 - 30px);
    color: #fff;
    position: relative;
    cursor: pointer;

    img {
        width: 100%;
        aspect-ratio: 1;
        object-fit: cover;
        object-position: top;
        margin-bottom: 15px;
    }

    span {
        display: none;
        position: absolute;
        text-align: center;
        top: 70px;
        left: 50%;
        transform: translate(-50%, 0);
    }

    &:hover img {
        opacity: .3;
    }

    &:hover span {
        display: block;
    }
}
</style>