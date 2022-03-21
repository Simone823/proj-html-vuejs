<template>
    
    <!-- Header -->
    <header>

        <!-- Telefon -->
        <div class="telefon">
            <span v-for="element in arrayNumber" :key="element.id">
                {{element.numero}}
            </span>
        </div>

        <!-- Icone social -->
        <div class="social">
            <ul>
                <li v-for="element in arrayIconSocial" :key="element.id">
                    <a :href="element.href">
                        <img :src="require(`../assets/images/${element.srcIcon}`)" :alt="element.id">
                    </a>
                </li>
            </ul>
        </div>

    </header>

</template>




<script>
export default {
    name: "MyHeader",

    data() {
        return {

            // Array numeri telefono
            arrayNumber: [
                {
                    id: "prefisso",
                    numero: "(001)",
                },

                {
                    id: "numero_1",
                    numero: "88451234"
                },

                {
                    id: "numero_2",
                    numero: "88455438"
                }
            ],

            // Array icone social 
            arrayIconSocial: [
                {
                    id: "facebook",
                    href: "#",
                    srcIcon: "facebook-icon.svg",
                },

                {
                    id: "twitter",
                    href: "#",
                    srcIcon: "twitter-icon.svg",
                },

                {
                    id: "pinterest",
                    href: "#",
                    srcIcon: "pinterest-icon.svg",
                },
            ],

        }
    }
}
</script>




<style lang="scss" scoped>
// Import scss common
@import "../assets/scss/common.scss";

header{
    background-color: $bkg-color-gray-light-shade;
    padding: 8px 44px 8px 68px;
    color: $text-color-white;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    row-gap: 10px;
    gap: 10px;

    .telefon {
        flex-shrink: 0;
        
        span:nth-child(1) {
            margin-right: 3px;
        }

        span:nth-child(2) {
            margin-right: 15px;
        }
    }

    .social {

        ul {
            display: flex;
            gap: 17px;

            li {
                cursor: pointer;
            }
        }

        img {
            width: 17px;
            height: 17px;
        }
    }
}

</style>