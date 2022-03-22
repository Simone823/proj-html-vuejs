<template>
    
    <!-- Sezione 4 -->
    <section class="section_4">

        <!-- Riga 1 -->
        <div class="row_1">
            <!-- Wrapper title -->
            <div class="wrapper_title col-5">
                <!-- Linea -->
                <div class="line"></div>
                <!-- Title -->
                <h3 class="title">
                    Our recent <span>web design</span> &amp; <br>
                    some example of <br>
                    past <span>projects</span>
                </h3>
                <!-- Linea -->
                <div class="line"></div>
            </div>

            <!-- Description wrapper -->
            <div class="description_wrapper col-7">
                <p class="description">
                    Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind <br>
                    texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language <br>
                    ocean. Separated they live in Bookmarksgrove. Far far away, behind the word mountains, far from the <br>
                    countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove.
                </p>
            </div>
        </div>

        <!-- Riga 2 -->
        <div class="row_2">
            <!-- Cards wrapper -->
            <div class="cards_wrapper">
                <!-- Card -->
                <div class="card col-3" v-for="(element, index) in arrayCards" :key="index">
                    <img :src="require(`../assets/images/${element.img}`)" alt="">
                </div>
            </div>

            <!-- Button -->
            <div class="btn">
                <button class="btn_readmore">
                    <a href="#">Read More</a>
                </button>
            </div>
        </div>

    </section>

</template>


<script>
export default {
    name: "Section_4",

    data() {
        return {
            // Array cards
            arrayCards: [
                {
                    img: "ina-soulis-227104-unsplash-1024x1024.jpg",
                },

                {
                    img: "sunisa-misa-531163-unsplash-1024x1024.jpg",
                },

                {
                    img: "355H-1024x1024.jpg",
                },

                {
                    img: "photo-1448932252197-d19750584e56-1024x1024.jpg",
                },

                {
                    img: "business-competition-PB366D8-1024x1024.jpg",
                },

                {
                    img: "cozy-sofa-in-living-room-PQR5AB9-1024x1024.jpg",
                },

                {
                    img: "cody-davis-253928-unsplash-1024x1024.jpg",
                },

                {
                    img: "aa9a4539-PQGJ7HU-1024x1024.jpg",
                },
            ],
        }
    }
}
</script>


<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.section_4 {
    padding: 215px 0;

    .col-3 {
        flex-basis: calc((100% / 12 - 5px) * 3);
    }
    
    .row_1 {
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        row-gap: 20px;
        margin-bottom: 53px;

        .wrapper_title {
            padding-left: 21px;

            .line {
                
                &:first-child {
                    margin-bottom: 52px;
                }

                &:last-child {
                    margin-top: 52px;
                }

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

            .title {
                color: $text-color-gray-dark;
                font-size: 48px;

                span {
                    color: $color-green;
                }
            }
        }

        .description_wrapper {
            align-self: flex-end;

            .description {
                color: $text-color-gray-dark;
            }
        }
    }

    .row_2 {

        .cards_wrapper {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
            margin-bottom: 118px;

            .card {
                aspect-ratio: 1/1;
                border-radius: 5px;
                overflow: hidden;
            }
        }

        .btn {
            text-align: center;

            .btn_readmore {
                border: none;
                padding: 20px 45px;
                border-radius: 31px;
                cursor: pointer;
                background-image: $bkg-color-gradient-green;
                color: $text-color-white;
                text-transform: uppercase;
                filter: drop-shadow(0 5px 8px rgba($color: $color-green, $alpha: 0.6));
            }
        }
    }
}
</style>