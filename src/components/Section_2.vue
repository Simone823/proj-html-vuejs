<template>

    <!-- Sezione 2 -->
    <section class="section_2">

        <!-- Info wrapper -->
        <div class="info_wrapper">
            <h2 class="title">
                We Are Here To <br>
                Make Your <span>Website</span> <br>
                Look More <span>Elegant</span> <br>
                And Stylish!
            </h2>

            <!-- Linea -->
            <div class="line"></div>

            <!-- Button -->
            <div class="btn">
                <button class="btn_view_all">
                    <a href="#">View All</a>
                </button>
            </div>
        </div>

        <!-- Cards wrapper -->
        <div class="cards_wrapper">

            <!-- Card -->
            <div class="card" v-for="(element, index) in arrayCards" :key="index">
                <!-- Img wrapper -->
                <div class="img_wrapper">
                    <img :src="require(`../assets/images/${element.img}`)" alt="">
                </div>
                <!-- Info_wrapper -->
                <div class="info_wrapper">
                    <h3 class="title">{{element.title}}</h3>
                    <p class="description">{{element.description}}</p>
                </div>
            </div>

        </div>

    </section>

</template>




<script>
export default {
    name: "Section_2",  
    
    data() {
        return {
            // Array cards
            arrayCards: [
                {
                    img: "speedometer_icon.svg",
                    title: "Speed Optimization",
                    description: "Far far away, behind the word mountains, far From the countries Vokalia Separated...",
                },

                {
                    img: "cloud_icon.svg",
                    title: "Cloud Solutions",
                    description: "Far far away, behind the word mountains, far From the countries Vokalia Separated...", 
                },

                {
                    img: "mobile_icon.svg",
                    title: "Website Design",
                    description: "Far far away, behind the word mountains, far From the countries Vokalia Separated...", 
                },

                {
                    img: "timer_icon.svg",
                    title: "Online Marketing",
                    description: "Far far away, behind the word mountains, far From the countries Vokalia Separated...", 
                }
            ],
        }
    }
}
</script>



<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.section_2 {
    padding: 210px 0;
    display: flex;
    align-items: center;
    gap: 90px;
    flex-wrap: wrap;

    .info_wrapper {
        flex-basis: calc((100% / 12) * 4);
        flex-grow: 1;
        padding: 0 21px;

        .title {
            font-size: 55px;
            color: $text-color-gray-dark;
            font-weight: 600;

            span {
                color: $color-green;
            }
        }

        .line {
            margin-top: 33px;
            margin-bottom: 59px;

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

        .btn {
            
            .btn_view_all {
                border: none;
                padding: 20px 45px;
                border-radius: 31px;
                cursor: pointer;
                background-image: $bkg-color-gradient-green;
                color: $text-color-white;
                text-transform: uppercase;
                filter: drop-shadow(8px 5px 8px rgba($color: $color-green, $alpha: 0.6));
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
        }
    }    

    .cards_wrapper {
        flex-basis: calc((100% / 12) * 8 - 90px);
        flex-grow: 1;
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        gap: 35px;
        padding: 8px 4px;

        .card {
            flex-basis: calc((100% / 12) * 6 - 35px);
            flex-grow: 1;
            border-radius: 31px;
            padding: 57px 47px;
            color: $text-color-gray-dark;
            background-color: $bkg-color-white;
            filter: drop-shadow(0 0 5px rgba($color: $bkg-color-gray-light-shade, $alpha: 0.2));

            &:hover {
                background-image: $bkg-color-gradient-green;
                opacity: 1;
                filter: drop-shadow(0 0 5px rgba($color: $color-green, $alpha: 0.4));
                animation: opacity 350ms linear;
                transform: scale(0.97);

                @keyframes opacity {
                    from {
                        opacity: 0;
                        filter: drop-shadow(0 0 5px rgba($color: $color-green, $alpha: 0));
                        transform: scale(1);
                    }

                    100% {
                        opacity: 1;
                        filter: drop-shadow(0 0 5px rgba($color: $color-green, $alpha: 0.4));
                        transform: scale(0.97);
                    }
                }

                .title {
                    color: $text-color-white;
                }

                .description {
                    color: $text-color-white;
                }

                .img_wrapper {
                    img {
                        filter: brightness(0%) invert(100%);
                    }
                }
            }

            .img_wrapper {
                width: 73px;
                height: 61px;
                margin-bottom: 39px;
            }

            .info_wrapper {
                padding: 0;

                .title {
                    font-size: 30px;
                    font-weight: 500;
                    margin-bottom: 24px;
                }
            }
        }
    }
}

@media screen and (max-width: 1326px) {
    .section_2 {
        flex-direction: column;
        align-items: flex-start;

        .cards_wrapper {
            padding: 8px 15px;
        }
    }
}

@media screen and (max-width: 825px) {

    .section_2 {
        .cards_wrapper {
            flex-direction: column;
        }

    }
}

</style>