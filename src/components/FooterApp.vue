<script>
import ShopBar from './ShopBarFooter.vue';
import Menu from './MenuFooter.vue';
import Socials from './SocialFooter.vue';
export default {
    components: {
        ShopBar,
        Menu,
        Socials
    }
}
</script>

<template>
    <footer>
        <ShopBar />
        <Menu />
        <Socials />
    </footer>
</template>

<style lang="scss" scoped>

</style>