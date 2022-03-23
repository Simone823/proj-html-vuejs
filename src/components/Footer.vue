<template>
    
    <!-- Sezione 8 -->
    <footer class="footer">

        <!-- List wrapper -->
        <div class="list_wrapper">

            <!-- List Item -->
            <div class="list_item" v-for="element in arrayList" :key="element.id">

                <!-- Logo -->
                <div class="logo" v-if="element.img">
                    <img :src="require(`../assets/images/${element.img}`)" alt="">
                </div>

                <!-- Description wrapper -->
                <div class="description" v-if="element.description">
                    <p>{{element.description}}</p>
                </div>

                <!-- Titolo -->
                <div class="title" v-if="element.title">
                    <h3>{{element.title}}</h3>
                </div>

                <!-- Linea -->
                <div class="line" v-if="element.line == true"></div>

                <!-- Mappa -->
                <div class="map" v-if="element.imgMap">
                    <a href="#">
                        <a :href="element.href">
                            <img :src="require(`../assets/images/${element.imgMap}`)" alt="">
                        </a>
                    </a>
                </div>

                <!-- Ul list link-->
                <ul v-if="element.links">
                    <li class="link" v-for="(link, index) in element.links" :key="index">
                        <!-- Link -->
                        <a :href="link.href">
                            {{link.name}} {{link.telefon}} {{link.email}} {{link.address}}
                        </a>
                    </li>
                </ul>
            </div>

        </div>

    </footer>

</template>


<script>
export default {
    name: "MyFooter",

    data () {
        return {
            // Array List Item
            arrayList: [
                {
                    id: 1,
                    img : "cropped-Group-39-2x.png",
                    description: "While the lovely teams with vapour around me, and the meridian sun strikes the upper surface of the impenetrable foliage of my trees. While the lovely vallety teems witch vapour around me.",
                    line: false,
                },

                {
                    id: 2,
                    title: "Quick Links",
                    line: true,
                    links: [
                        {
                            name: "Carrers",
                            href: "#",
                        },

                        {
                            name: "News",
                            href: "#",
                        },

                        {
                            name: "Terms of use",
                            href: "#",
                        },

                        {
                            name: "Privacy Projects",
                            href: "#",
                        },

                        {
                            name: "About",
                            href: "#",
                        },

                        {
                            name: "Contact",
                            href: "#",
                        }
                    ],
                },

                {
                    id: 3,
                    title: "Contact",
                    line: true,
                    links: [
                        {
                            address: "Patricia C. Amedee 4401 Waldeck Street Grapevine Nashville, TX 76051",
                        },

                        {
                            email: "info@yourdomain.com",
                            href: "#",
                        },

                        {
                            telefon: "+99 (0) 101 0000 888",
                        }
                    ],
                },

                {
                    id: 4,
                    title: "Location On Map",
                    line: true,
                    map: true,
                    imgMap: "map.png",
                    href: "#", 
                }
            ],
        }
    }
}
</script>



<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.footer {
    padding: 140px 0;

    .list_wrapper {
        padding: 0 30px;
        display: flex;
        flex-wrap: wrap;
        gap: 41px;

        .list_item {
            flex-basis: calc((100% / 12) * 3 - 41px);
            flex-grow: 1;

            a {
                font-size: 16px;
                font-weight: 400;
                color: $text-color-gray-dark;
            }

            &:nth-child(2) {

                ul {
                    .link {
                        margin-bottom: 12px;

                        &:last-child {
                            margin-bottom: 0;
                        }
                    }
                }

            }

            &:nth-child(3) {

                ul {

                    .link {
                        margin-bottom: 36px;

                        &:first-child {
                            max-width: 300px;
                        }

                        &:last-child {
                            margin-bottom: 0;
                        }
                    }
                }
            }

            .logo {
                margin-bottom: 22px;
            }

            .title {

                h3 {
                    text-transform: uppercase;
                    color: $text-color-gray-dark;
                    font-size: 23px;
                    font-weight: 700;
                }
            }

            .line {
                margin-top: 22px;
                margin-bottom: 35px;

                &::before {
                    content: '';
                    display: inline-block;
                    width: 9px;
                    height: 5px;
                    margin-right: 6px;
                    background-image: $bkg-color-gradient-green;
                    border-radius: 8px;
                }

                &::after {
                    content: '';
                    display: inline-block;
                    width: 48px;
                    height: 5px;
                    background-image: $bkg-color-gradient-green;
                    border-radius: 8px;
                }
            }

            .map {
                img {
                    width: 100%;
                }
            }
        }
    }
}

</style>