<template>
    
    <!-- Sezione 6 -->
    <section class="section_6">

        <!-- Riga 1 -->
        <div class="row">

            <!-- Title wrapper -->
            <div class="title_wrapper">
                <!-- Title -->
                <h3 class="title">Latest News &#38; Our <span>Blog</span></h3>
                <!-- Linea -->
                <div class="line"></div>
            </div>

            <!-- Cards wrapper -->
            <div class="cards_wrapper">
                <!-- Card -->
                <div class="card" v-for="(element, index) in arrayCards" :key="index">
                    <!-- Img wrapper -->
                    <div class="img_wrapper">
                        <img :src="require(`../assets/images/${element.img}`)" alt="">
                    </div>
                    <!-- Info wrapper -->
                    <div class="info_wrapper">
                        <p class="date">{{element.date}}</p>
                        <h3 class="news_title">{{element.newsTitle}}</h3>
                    </div>
                </div>
            </div>

            <!-- Button -->
            <div class="btn">
                <button class="btn_view_all">
                    <a href="#">View All Post</a>
                </button>
            </div>

        </div>

    </section>

</template>


<script>
export default {
    name: "Section_6",

    data() {
        return {
            // Array cards
            arrayCards: [
                {
                    img: "serious-businesswoman-with-documents-talking-on-P9Q6LX6-1024.jpg",
                    date: "May 24, 2018 by Alex",
                    newsTitle: "Marketings Ideas",
                },

                {
                    img: "Businessman-at-the-desk-in-his-office-resting--1024x768.jpg",
                    date: "May 24, 2018 by Alex",
                    newsTitle: "Rest During Working Hours",
                },

                {
                    img: "simple-home-office-with-tree-PBXRXYB-large-1024x768.jpg",
                    date: "May 24, 2018 by Alex",
                    newsTitle: "Develop Your Start Up Idea",
                },
            ],
        }
    }
}
</script>


<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.section_6 {
    padding: 246px 0;

    .title_wrapper {
        text-align: center;
        margin-bottom: 33px;
        
        .title {
            font-size: 55px;
            font-weight: 600;

            span {
                color: $color-green;
            }
        }

        .line {
            margin-top: 61px;

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
    }

    .cards_wrapper {
        display: flex;
        flex-wrap: wrap;
        flex: 1;
        padding: 0 6px;
        gap: 30px;
        margin-bottom: 62px;

        .card {
            flex-basis: calc((100% / 12) * 4 - 30px);
            flex-grow: 1;
            flex-shrink: 1;
            aspect-ratio: 1/1;

            .img_wrapper {
                max-width: 100%;
                border-top-left-radius: 8px;
                border-top-right-radius: 8px;
                border-bottom-left-radius: 12px;
                border-bottom-right-radius: 12px;
                overflow: hidden;
                filter: drop-shadow(0 0 8px rgba($color: $bkg-color-gray-light-shade, $alpha: 0.2)); 
            }

            .info_wrapper {
                width: calc((100% / 12) * 10);
                background-color: $bkg-color-white;
                filter: drop-shadow(0 0 5px rgba($color: $bkg-color-gray-light-shade, $alpha: 0.2));
                border-radius: 8px;
                padding: 46px 44px;
                position: relative;
                margin: 0 auto;
                top: -100px;

                .date {
                    color: $text-color-gray-light;
                    font-weight: 500;
                    margin-bottom: 14px;
                }

                .news_title {
                    color: $text-color-gray-dark;
                    font-size: 24px;

                    &::before {
                        content: '';
                        display: inline-block;
                        width: 10px;
                        height: 10px;
                        background-color: $color-green;
                        border-radius: 50%;
                        transform: translateY(-50%);
                        margin-right: 10px;
                    }
                }
            }
        }
    }

    .btn {
        text-align: center;
        
        .btn_view_all {
            border: none;
            padding: 20px 45px;
            border-radius: 31px;
            cursor: pointer;
            background-image: $bkg-color-gradient-gray-dark;
            color: $text-color-white;
            text-transform: uppercase;
            filter: drop-shadow(8px 5px 8px rgba($color: $bkg-color-gray-light-shade, $alpha: 0.6));
        }
    }
}

</style>