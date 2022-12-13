<script>
export default {
    data() {
        return {
            shopArr: [
                {
                    icon: 'buy-comics-digital-comics.png',
                    text: 'DIGITAL COMICS',
                    link: '#',
                },
                {
                    icon: 'buy-comics-merchandise.png',
                    text: 'DC MERCHANDISE',
                    link: '#',
                },
                {
                    icon: 'buy-comics-subscriptions.png',
                    text: 'SUBSCRIPTION',
                    link: '#',
                },
                {
                    icon: 'buy-comics-shop-locator.png',
                    text: 'COMIC SHOP LOCATOR',
                    link: '#',
                },
                {
                    icon: 'buy-dc-power-visa.svg',
                    text: 'DC POWER VISA',
                    link: '#',
                },
            ],
        }
    },
    methods: {
        getImagePath: function (imgUrl) {
            return new URL(imgUrl, import.meta.url).href;
        },
    },
}
</script>

<template>
    <section>
        <div class="container">
            <div v-for="(shopOpt, index) in shopArr" :key="index">
                <a :href="shopOpt.link">
                    <img :src="getImagePath('./../assets/img/' + shopOpt.icon)" :alt="shopOpt.text">
                    {{ shopOpt.text }}
                </a>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use './../style/partials/variables.scss';
@use './../style/partials/mixIn.scss';

section {
    background-color: variables.$blue-DC;
    height: 150px;
    color: #fff;

    .container {
        @include mixIn.center(vertical);
        justify-content: space-between;
        height: 100%;

        div {
            width: fit-content;
            border-radius: 2px;
            overflow: hidden;

            a {
                padding: 5px;
                line-height: 55px;
                @include mixIn.center(vertical);
                column-gap: 8px;

                img {
                    height: 55px;
                }
            }

            &:hover {
                background: lighten(variables.$blue-DC, 20%);
            }
        }
    }
}
</style>