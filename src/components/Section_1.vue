<template>
    
    <!-- Sezione 1 -->
    <section class="section_1">
        
        <!-- Wrapper descrizione -->
        <div class="wrapper_slider" v-for="(element, index) in arraySlide" :key="index" :style="`background-image: url(${element.img})`" :class="index == indexActiveSlide ? 'active' : ''">

            <div class="slider_item" @mouseleave="autoPlay()" @mouseenter="stopPlay()">
                <!-- Wrapper title -->
                <div class="wrapper_title">
                    <h3>{{element.title}}</h3>
                    <h1 v-html="element.subtitle"></h1>
                </div>

                <!-- Linea -->
                <div class="line"></div>

                <!-- Description -->
                <div class="description">
                    <p>{{element.description}}</p>
                </div>

                <!-- Button -->
                <div class="btn">
                    <button class="btn_readmore">
                        <a :href="element.href">Read More</a>
                    </button>
                </div>

                <!-- Footer wrapper card -->
                <div class="footer_card">
                    <!-- Lista social -->
                    <ul class="social">
                        <li v-for="element in element.arraySocial" :key="element.id">
                            <a :href="element.href">{{element.id}}</a>
                        </li>
                    </ul>

                    <!-- Controls -->
                    <div class="controls">
                        <div class="slide_number" :class="index == indexActiveSlide ? 'active' : ''" 
                            v-for="(element, index) in arraySlide" :key="index"
                            @click="changeSlide(index)"
                        >
                            {{element.slide}}
                        </div>
                    </div>
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

            // Array slides
            arraySlide: [
                {
                    slide: "01",
                    img: require(`../assets/images/Group-36-2x.png`),
                    title: "17 Years of experience",
                    subtitle: `We Are a <br> Web Design <span style="color: #00d9a6;">Agency</span>`,
                    description: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large ocean. Separated they live in Bookmarksgrove.",
                    href: "#",
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
                },

                {
                    slide: "02",
                    img: require(`../assets/images/Group-35-2x.png`),
                    title: "17 Years of experience",
                    subtitle: `Focus on your <br> <span style="color: #00d9a6;">Business</span>`,
                    description: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large ocean. Separated they live in Bookmarksgrove.",
                    href: "#",
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
                },

                {
                    slide: "03",
                    img: require(`../assets/images/Group-40-2x.png`),
                    title: "17 Years of experience",
                    subtitle: `A group of <br> Expert <span style="color: #00d9a6;">Planners</span>`,
                    description: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large ocean. Separated they live in Bookmarksgrove.",
                    href: "#",
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
                },
            ],

            // Indice attivo slide
            indexActiveSlide: 0,

            // File audio slide flip
            audioCardFlip: new Audio(require('../assets/audio/Card-flip-sound-effect.wav')),
        }
    },

    created: function() {
        this.autoPlay();
    },

    methods: {

        // Funzione che al click imposta il valore di indexActiveSlide = indice dell'elemento
        changeSlide: function (i) {
            this.indexActiveSlide = i;

            // Play audio slide flip
            this.audioCardFlip.play();
            this.audioCardFlip.volume = 0.1;
        },

        // Funzione che incrementa indexActiveSlide 
        changeSlideAutoPlay: function() {

            // Se l'indice attivo è minore di 2
            if (this.indexActiveSlide < this.arraySlide.length -1) {
                this.indexActiveSlide++;
            } // E se l'indice attivo è = a 2
              else if (this.indexActiveSlide == this.arraySlide.length -1) {
                this.indexActiveSlide = 0;
            }
        },

        // Autoplay
        autoPlay: function(){
            this.intervallo = setInterval(this.changeSlideAutoPlay, 2800);
        },

        // Stop Autoplay
        stopPlay: function(){
            clearInterval(this.intervallo);
        }
    }
}
</script>



<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.section_1 {
    padding-left: 105px;
    background-color: $bkg-color-gray-light;
 
    .wrapper_slider {
        width: 100%;
        background-repeat: no-repeat;
        background-size: 78%;
        background-position: center left 145%;
        display: none;
        opacity: 0;

        &.active {
            display: block;
            opacity: 1;
            animation: display 680ms linear;

            @keyframes display {
                from {
                    opacity: 0;
                    display: none;
                }

                50% {
                    display: block;
                }

                100% {
                    opacity: 1;
                }
            }
        }

        .slider_item {
            max-width: 695px;
            padding-top: 127px;
            position: relative;

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
            
            .footer_card {
                padding-bottom: 127px;
                display: flex;
                justify-content: space-between;
                align-items: center;
                gap: 20px;

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


}

@media screen and (max-width: 825px) {
    .footer_card {
        flex-direction: column;
    }
}

@media screen and (max-width: 768px) {
    .section_1 {
        padding: 10px;
    }
}

@media screen and (max-width: 375px) {
    .social {
        justify-content: center;
    }
}


</style>