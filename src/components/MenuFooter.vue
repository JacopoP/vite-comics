<script>
export default {
    data() {
        return {
            lists: [
                {
                    title: 'DC COMICS',
                    links: ['Characters', 'Comics', 'Movies', 'TV', 'Games', 'Videos', 'News']
                },
                {
                    title: 'SHOP',
                    links: ['Shop DC', 'Shop DC Collectibles',]
                },
                {
                    title: 'DC',
                    links: ['Terms Of Use', 'Privacy policy (new)', 'Ad Choices', 'Advertising', 'Jobs', 'Subscription', 'Talent Workshop', 'CPSC Certificates', 'Ratings', 'Shop Help', 'Contact Us']
                },
                {
                    title: 'SITES',
                    links: ['DC', 'MAD Magazine', 'DC Kids', 'DC Universe', 'DC Power Visa']
                },
            ],
            img: 'dc-logo-bg.png',
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
            <div id="list-container">
                <div v-for="list in lists">
                    <h3>{{ list.title }}</h3>
                    <ul>
                        <li v-for="(link, index) in list.links" :key="index"><a href="#">{{ link }}</a></li>
                    </ul>
                </div>
            </div>
            <img :src="getImagePath('./../assets/img/' + img)" alt="logo DC">
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use './../style/partials/mixIn.scss' as *;

section {
    height: 370px;
    background: url('./../assets/img/footer-bg.jpg');
    background-size: cover;
    overflow: hidden;

    .container {
        justify-content: space-between;
        @include center(vertical);
        height: 100%;

        #list-container {
            @include my-display-flex;
            flex-direction: column;
            flex-wrap: wrap;
            gap: 20px 35px;
            height: 100%;
            padding: 40px 0;

            h3 {
                color: #fff;
                margin-bottom: 15px;
            }

            ul {
                li {
                    color: #fff;
                    font-size: .85rem;
                    opacity: .5;
                    margin: 4px 0;

                    &:hover {
                        opacity: 1;
                    }
                }
            }
        }
    }
}
</style>