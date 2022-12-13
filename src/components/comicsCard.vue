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
        {{ comic.series }}
    </div>
</template>

<style lang="scss" scoped>
.card {
    flex-basis: calc(100% / 6 - 30px);
    color: #fff;

    img {
        width: 100%;
        aspect-ratio: 1;
        object-fit: cover;
        object-position: top;
        margin-bottom: 15px;
    }
}
</style>