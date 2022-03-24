<template>
    
    <!-- Sezione 7 -->
    <section class="section_7">

        <!-- Cards wrapper -->
        <div class="cards_wrapper">
            <!-- Card -->
            <div class="card" v-for="(element, index) in arrayCards" :key="index">
                <!-- Info wrapper -->
                <div class="info_wrapper">
                    <!-- Commento -->
                    <p class="commento">{{element.commento}}</p>
                    <!-- Titolo -->
                    <h3 class="title">{{element.title}}</h3>
                    <!-- Input email -->
                    <div class="input" v-if="element.button == 'form'">
                        <!-- input -->
                        <input type="email" placeholder="Enter Your Email Address">
                        <!-- submit -->
                        <button class="submit">Submit</button>
                    </div>
                    <!-- Button -->
                    <button class="btn_startnow" v-else>
                        <a :href="element.link">{{element.button}}</a>
                    </button>
                </div>
            </div>
        </div>

        <!-- Sponsor banner -->
        <div class="sponsor_wrapper">
            <!-- Sponsor -->
            <div class="sponsor" v-for="element in arraySponsor" :key="element.id">
                <img :src="require(`../assets/images/${element.img}`)" alt="">
            </div>
        </div>

    </section>

</template>



<script>
export default {
    name: "Section_7",

    data () {
        return {
            // Array cards 
            arrayCards: [

                {
                    commento: "Are You Ready?",
                    title: "Start A New Project",
                    button: "form",
                    link: "",
                },

                {
                    commento: "What Are You Waiting for?",
                    title: "Let's Talk About Work",
                    button: "Start Now",
                    link: "#",
                },
            ],

            // Array sponsor
            arraySponsor: [
                {
                    id: 1,
                    img: "client-1-2x.png",
                },

                {
                    id: 2,
                    img: "client-9-2x.png",
                },

                {
                    id: 3,
                    img: "client-7-2x.png",
                },

                {
                    id: 4,
                    img: "client-3-2x.png",
                },

                {
                    id: 5,
                    img: "client-4-2x.png",
                },

                {
                    id: 6,
                    img: "client-5-2x.png",
                },
            ],
        }
    }
}
</script>


<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.section_7 {
    background-color: $bkg-color-gray-light;
    padding-bottom: 127px;

    .cards_wrapper {
        display: flex;
        flex-wrap: wrap;
        padding: 4px 8px;
        gap: 29px;
        margin-bottom: 121px;

        .card {
            flex-basis: calc((100% / 12) * 6);
            flex-grow: 1;
            flex-shrink: 0;
            background-image: $bkg-color-gradient-gray-dark;
            border-radius: 20px;
            padding: 72px 15px;
            filter: drop-shadow(0 0 8px rgba($color: $bkg-color-gray-light-shade, $alpha: 0.5)); 
            display: flex;
            align-items: center;
            justify-content: center;

            &:nth-child(2) {
                flex-basis: calc((100% / 12) * 6 - 29px);
                background-image: $bkg-color-gradient-green;
                filter: drop-shadow(0 0 8px rgba($color: $color-green, $alpha: 0.5));
            }

            .info_wrapper {
                text-align: center;

                .commento {
                    color: $text-color-gray-light;
                    font-size: 18px;
                    font-weight: 500;
                    margin-bottom: 20px;
                }
    
                .title {
                    color: $text-color-white;
                    font-size: 40px;
                    font-weight: 700;
                    margin-bottom: 64px;
                }

                .input {
                    position: relative;

                    input[type="email"] {
                        width: 100%;
                        padding: 25px 42px;
                        padding-right: 108px;
                        background-color: $bkg-color-gray-light-shade;
                        border-radius: 50px;
                        border: none;
                        font-size: 16px;
                        color: $text-color-gray-light;
                        
                    }

                    button {
                        border: none;
                        position: absolute;
                        right: 25px;
                        top: 50%;
                        transform: translateY(-50%);
                        background-color: transparent;
                        text-transform: uppercase;
                        color: $text-color-gray-light;
                        cursor: pointer;
                        padding: 4px;
                        font-weight: 600;
                    }
                }


                .btn_startnow {
                    border: none;
                    padding: 20px 45px;
                    border-radius: 31px;
                    cursor: pointer;
                    background-image: $bkg-color-gradient-gray-dark;
                    color: $text-color-white;
                    text-transform: uppercase;
                    filter: drop-shadow(0 0 8px rgba($color: $bkg-color-gray-light-shade, $alpha: 0.6));
                    color: $text-color-gray-light;
                    position: relative;

                    a {
                        z-index: 1;
                        position: relative;

                    }

                    &:hover a{
                        color: $text-color-white;
                        transition: color 300ms linear;
                    }

                    &:hover::after {
                        @include hoverGray;
                        background-image: $bkg-color-gradient-green;
                        filter: drop-shadow(8px 5px 8px rgba($color: $color-green, $alpha: 0.6));
                    }
                }
            }
        }
    }

    .sponsor_wrapper {
        max-width: calc((100% / 12) * 12);
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        gap: 15px;

        .sponsor {
            flex-basis: calc((100% / 12) * 2 - 15px);
            flex-grow: 1;
            flex-shrink: 1;
            height: 70px;
            padding: 5px 0;

            img {
                margin: 0 auto;
            }
        }
    }
}

@media screen and (max-width: 1000px) {
    .section_7 {

        .sponsor_wrapper {
            .sponsor {
                flex-basis: calc((100% / 12) * 3 - 15px);
            }
        }
    }
}

@media screen and (max-width: 825px) {
    .section_7 {

        .sponsor_wrapper {
            .sponsor {
                flex-basis: calc((100% / 12) * 4 - 15px);
            }
        }
    }
}

@media screen and (max-width: 768px) {
    .section_7 {
        .cards_wrapper {
            flex-direction: column;
        }

        .sponsor_wrapper {
            .sponsor {
                flex-basis: calc((100% / 12) * 6 - 15px);
            }
        }
    }
}

@media screen and (max-width: 550px) {
    .section_7 {

        .sponsor_wrapper {
            .sponsor {
                flex-basis: calc((100% / 12) * 12 - 15px);
            }
        }
    }
}

</style>