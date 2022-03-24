<template>
    
    <!-- Sezione 1 -->
    <section class="section_1">
        
        <!-- Wrapper descrizione -->
        <div class="wrapper">

            <!-- Wrapper title -->
            <div class="wrapper_title">
                <h3>17 Years of experience</h3>
                <h1>We Are a <br> Web Design <span>Agency</span></h1>
            </div>

            <!-- Linea -->
            <div class="line"></div>

            <!-- Description -->
            <div class="description">
                <p>
                    Far far away, behind the word mountains, far from the countries Vokalia and Consonantia,
                    there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the
                    Semantics, a large ocean. Separated they live in Bookmarksgrove.
                </p>
            </div>

            <!-- Button -->
            <div class="btn">
                <button class="btn_readmore">
                    <a href="#">Read More</a>
                </button>
            </div>

            <!-- Footer wrapper card -->
            <div class="footer_card">
                <!-- Lista social -->
                <ul class="social">
                    <li v-for="element in arraySocial" :key="element.id">
                        <a :href="element.href">{{element.id}}</a>
                    </li>
                </ul>

                <!-- Controls -->
                <div class="controls">
                    <div class="slide_number active">01</div>
                    <div class="slide_number">02</div>
                    <div class="slide_number">03</div>        
                </div>
            </div>

        </div>

    </section>

</template>



<script>
export default {
    name: "Section_1",   
    
    data() {
        return {
            // Array icone e link social
            arraySocial: [
                {
                    id: "Facebook",
                    href: "#",
                },

                {
                    id: "Instagram",
                    href: "#",
                },

                {
                    id: "Youtube",
                    href: "#",
                },

                {
                    id: "Twitter",
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

.section_1 {
    padding: 127px 0;
    padding-left: 105px;
    background-color: $bkg-color-gray-light;
    background-image: url("../assets/images/Group-36-2x.png");
    background-repeat: no-repeat;
    overflow: hidden;
    background-size: 78%;
    background-position: center left 145%;

    .wrapper {
        max-width: 695px;

        .wrapper_title {

            h3 {
                font-size: 14px;
                text-transform: uppercase;
                letter-spacing: 10px;
                color: $color-green;
                margin-bottom: 26px;
            }

            h1 {
                font-weight: 700;
                font-size: 65px;
                color: $text-color-gray-dark;

                span {
                    color: $color-green;
                }
            }
        }

        .line {
            margin-top: 33px;
            margin-bottom: 45px;

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

        .description {
            p {
                margin-bottom: 49px;
                color: $text-color-gray-dark;
            }
        }

        .btn {
            margin-bottom: 58px;

            .btn_readmore {
                border: none;
                padding: 20px 45px;
                border-radius: 31px;
                cursor: pointer;
                background-image: $bkg-color-gradient-gray-dark;
                color: $text-color-white;
                text-transform: uppercase;
                position: relative;

                a {
                    z-index: 1;
                    position: relative;
                }

                &:hover::after {
                    @include hoverGray;
                    background-image: $bkg-color-gradient-green;
                }
            }
        }

        .social {
            display: flex;
            align-items: center;
            flex-wrap: wrap;

            li {
                text-transform: uppercase;
                font-weight: 700;
                color: $text-color-gray-dark;

                &:not(:last-child)::after{
                    content: '-';
                    display: inline;
                    margin-left: 8px;
                    margin-right: 8px;
                }

                a {
                    @include hoverLinkGray;
                }
            }
        }

        .footer_card {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;

            .controls {
                width: 194px;
                height: 52px;
                background-image: $bkg-color-gradient-gray-dark;
                border-radius: 31px;
                display: flex;
                align-items: center;
                justify-content: center;
                padding: 4px 4px;

                .slide_number {
                    color: $text-color-white;
                    width: calc(100% /3);
                    height: 100%;
                    border-radius: 31px;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    cursor: pointer;
                    color: $text-color-gray-light;
                    font-weight: 700;

                    &.active {
                        background-image: $bkg-color-gradient-green;
                    }
                }
            }
        }
    }
}


</style>