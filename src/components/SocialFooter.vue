<script>
export default {
    data() {
        return {
            socials: [
                {
                    name: 'Facebook',
                    logo: 'footer-facebook.png',
                    link: '#',
                },
                {
                    name: 'Twitter',
                    logo: 'footer-twitter.png',
                    link: '#',
                },
                {
                    name: 'YouTube',
                    logo: 'footer-youtube.png',
                    link: '#',
                },
                {
                    name: 'Pinterest',
                    logo: 'footer-pinterest.png',
                    link: '#',
                },
                {
                    name: 'Periscope',
                    logo: 'footer-periscope.png',
                    link: '#',
                },
            ]
        }
    },
    methods: {
        getImagePath: function (imgUrl) {
            return new URL(imgUrl, import.meta.url).href;
        }
    }
}
</script>

<template>
    <section>
        <div class="container">
            <a href="#">Sign-up now</a>
            <div id="cta">
                <span>FOLLOW US &nbsp;</span>
                <a v-for="(social, index) in socials" :href="social.link" :key="index">
                    <img :src="getImagePath('./../assets/img/' + social.logo)" :alt="social.name">
                </a>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use './../style/partials/mixIn.scss' as *;
@use './../style/partials/variables.scss';

section {
    height: 100px;
    background-color: #303030;

    .container {
        @include center(vertical);
        justify-content: space-between;
        height: 100%;

        >a {
            background-color: transparent;
            border: 3px solid variables.$blue-DC;
            color: #fff;
            font-size: 1.3rem;
            padding: 10px 13px;

            &:hover {
                background-color: rgba(255, 255, 255, .4);
            }
        }

        #cta {
            color: variables.$blue-DC;
            font-weight: bold;
            font-size: 1.1rem;

            * {
                vertical-align: middle;
                margin: 0 4px;
            }
        }
    }
}
</style>