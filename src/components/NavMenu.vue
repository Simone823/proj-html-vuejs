<template>

    <!-- Nav -->
    <nav>

        <!-- Logo -->
        <figure class="logo" v-for="(element, index) in arrayLogo" :key="index">
            <a :href="element.href">
                <img :src="require(`../assets/images/${element.srcLogo}`)" alt="">
            </a>
        </figure>

        <!-- Lista menu -->
        <ul class="menu">
            <li v-for="(element, index) in arrayMenulist" :key="index">
                <a :href="element.href">{{element.name}}</a>
            </li>
        </ul>

        <!-- Buttons -->
        <div class="btn">
            <button class="btn_purchase btn_hover_gray"><a href="#">Purchase</a></button>
            <button class="btn_search">
                <img src="../assets/images/search-icon.svg" alt="">
            </button>
        </div>

    </nav>

</template>




<script>
export default {
    name: "NavMenu",

    data () {
        return {
            // Array Logo Nav
            arrayLogo: [
                {
                    href: "#",
                    srcLogo: "cropped-Group-39-2x.png",
                }
            ],

            // Array menu list
            arrayMenulist: [
                {
                    href: "#",
                    name: "Home",
                },

                {
                    href: "#",
                    name: "About",
                },

                {
                    href: "#",
                    name: "Services",
                },

                {
                    href: "#",
                    name: "Showcase",
                },

                {
                    href: "#",
                    name: "Blog",
                },

                {
                    href: "#",
                    name: "Contact",
                }
            ],
        }
    }
}
</script>



<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

nav {
    padding: 24px 43px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    row-gap: 20px;
    gap: 25px;
    position: sticky;
    top: 0;
    background-color: $bkg-color-white;
    z-index: 999999;
    box-shadow: 0 2px 10px rgba($color: $text-color-gray-dark, $alpha: 0.4);

    .logo {
        width: 198px;
    }

    .menu {
        display: flex;
        align-items: center;
        gap: 36px;
        flex-wrap: wrap;

        li a {
            text-transform: uppercase;
            font-weight: 500;
            cursor: pointer;
            @include hoverLinkGray;
        }
    }

    .btn {
        display: flex;
        align-items: center;
        gap: 32px;

        .btn_purchase {
            border: none;
            padding: 20px 42px;
            border-radius: 31px;
            text-transform: uppercase;
            color: $text-color-white;
            cursor: pointer;
            background-image: $bkg-color-gradient-green;
            font-weight: 500;
            filter: drop-shadow(2px 2px 8px rgba($color: $color-green, $alpha: 0.6));
            position: relative;

            a {
                z-index: 1;
                position: relative;
            }

            &:hover {
                filter: drop-shadow(8px 5px 8px rgba($color: $bkg-color-gray-light-shade, $alpha: 0.6));
                transition: all 250ms linear;
            }

            &:hover::after {
                @include hoverGray;
                background-image: $bkg-color-gradient-gray-dark;
            }
        }

        .btn_search {
            width: 19px;
            height: 19px;
            border: none;
            background: none;
            cursor: pointer;
        }
    }
}

</style>