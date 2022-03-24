<template>
    
    <!-- Sezione 4 -->
    <section class="section_4">

        <!-- Riga 1 -->
        <div class="row_1">
            <!-- Wrapper title -->
            <div class="wrapper_title">
                <!-- Linea -->
                <div class="line"></div>
                <!-- Title -->
                <h3 class="title">
                    Our recent <span>web design</span> &amp;
                    some example of <br>
                    past <span>projects</span>
                </h3>
                <!-- Linea -->
                <div class="line"></div>
            </div>

            <!-- Description wrapper -->
            <div class="description_wrapper">
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
                <div class="card" v-for="(element, index) in arrayCards" :key="index">

                    <img :src="require(`../assets/images/${element.img}`)" alt="">

                    <!-- Hover Description -->
                    <div class="hover_description">
                        <h1>{{element.name}}</h1>
                        <p>{{element.type}}</p>
                    </div>
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
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
                },

                {
                    img: "sunisa-misa-531163-unsplash-1024x1024.jpg",
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
                },

                {
                    img: "355H-1024x1024.jpg",
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
                },

                {
                    img: "photo-1448932252197-d19750584e56-1024x1024.jpg",
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
                },

                {
                    img: "business-competition-PB366D8-1024x1024.jpg",
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
                },

                {
                    img: "cozy-sofa-in-living-room-PQR5AB9-1024x1024.jpg",
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
                },

                {
                    img: "cody-davis-253928-unsplash-1024x1024.jpg",
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
                },

                {
                    img: "aa9a4539-PQGJ7HU-1024x1024.jpg",
                    name: "A Famous Ferril Wheel",
                    type: "Marketing",
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

    .row_1 {
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        row-gap: 20px;
        margin-bottom: 53px;
        gap: 62px;

        .wrapper_title {
            flex-basis: calc((100% / 12) * 5);
            flex-grow: 1;
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
                font-size: 55px;
                font-weight: 600;

                span {
                    color: $color-green;
                }
            }
        }

        .description_wrapper {
            flex-basis: calc((100% / 12) * 7 - 62px);
            flex-grow: 1;
            align-self: flex-end;
            justify-content: flex-end;

            .description {
                font-size: 16px;
                line-height: 24px;
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
                flex-basis: calc((100% / 12 - 5px) * 3);
                flex-grow: 1;
                aspect-ratio: 1/1;
                border-radius: 5px;
                overflow: hidden;
                position: relative;

                 img {
                    object-fit: cover;
                    object-position: center;
                }

                .hover_description {
                    position: absolute;
                    left: 47px;
                    bottom: 63px;
                    color: $text-color-white;
                    opacity: 0;
                    z-index: 2;

                    h1 {
                        margin-bottom: 18px;
                    }

                    p {
                        text-transform: uppercase;
                        font-weight: 500;
                    }
                }

                &:hover {
                    transform: scale(0.97);
                    animation: cardHover 300ms linear;

                    &::after {
                        content: '';
                        display: block;
                        position: absolute;
                        top: 50%;
                        left: 50%;
                        transform: translateX(-50%) translateY(-50%);
                        width: 100%;
                        height: 100%;
                        background-image: $bkg-color-gradient-green;
                        animation: bkg 300ms linear;
                        opacity: 0.8;
                    }

                    .hover_description {
                        opacity: 1;
                        transition: opacity 300ms linear;
                    }

                    @keyframes cardHover {
                        from {
                            transform: scale(1);
                        }

                        100% {
                            transform: scale(0.97);
                        }
                    }
                }
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
}

@media screen and (max-width: 1000px) {
    .section_4 {

        .row_1 {
            flex-direction: column;

            .description_wrapper {
                align-self: flex-start;
            }
        }
    }
}

@media screen and (max-width: 768px) {

    .section_4 {
        .row_2 {
            .cards_wrapper {
                .card {
                    flex-basis: calc((100% / 12) * 6 - 5px);
                }
            }
        }
    }
}

@media screen and (max-width: 500px) {
    .section_4 {

        .row_2 {
            .cards_wrapper {
                padding: 0 15px;

                .card {
                    flex-basis: calc((100% / 12) * 12 - 5px);
                }
            }
        }
    }
}
</style>