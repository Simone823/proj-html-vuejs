<template>

    <!-- Footer banner -->
    <div class="footer_banner">

        <!-- Copyright -->
        <div class="copyright">
            <h2>&copy; 2020 Phlox Business Theme.</h2>
        </div>

        <!-- Social -->
        <div class="social">
            <!-- Icon -->
            <ul>
                <li class="icon" v-for="(element, index) in arraySocial" :key="index">
                    <a :href="element.href">
                        <img :src="require(`../assets/images/${element.icon}`)" alt="">
                    </a>
                </li>
            </ul>
        </div>

        <!-- Arrow up -->
        <div class="arrow_up" @click="scrollUp()">
            <img src="../assets/images/arrowUp_icon.svg" alt="">
        </div>

    </div>
    
</template>


<script>
export default {
    name: "FooterBanner",

    data() {
        return {
            arraySocial: [
                {
                    id: "facebook",
                    icon: "facebook-icon.svg",
                    href: "#",
                },

                {
                    id: "twitter",
                    icon: "twitter-icon.svg",
                    href: "#",
                },

                {
                    id: "pinterest",
                    icon: "pinterest-icon.svg",
                    href: "#",
                }
            ],
        }
    },

    methods: {
        // Funzione click Scrool up
        scrollUp: function() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    }
}
</script>


<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.footer_banner {
    padding: 45px 35px;
    background-image: $bkg-color-gradient-gray-dark;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;

    .copyright {
        h2 {
            text-transform: uppercase;
            font-size: 14px;
            font-weight: 500;
            color: $text-color-gray-light;
        }
    }

    .social {

        ul {
            display: flex;
            gap: 17px;
        }

        .icon {
            width: 17px;
            height: 17px;
        }
    }

    .arrow_up {
        width: 35px;
        height: 35px;
        position: fixed;
        bottom: 52px;
        right: 120px;
        background-color: $bkg-color-white;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        box-shadow: 0 0 2px $bkg-color-gray-light-shade;
        z-index: 8;

        img {
            width: 18px;
            height: 18px;
        }
    }
}
</style>