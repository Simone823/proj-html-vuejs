<template>
    
    <!-- Sezione 3 -->
    <section class="section_3">

        <!-- Img wrapper -->
        <div class="img_wrapper">
            <!-- Img wrapper 1 -->
            <div class="img_1_wrapper">
                <img src="../assets/images/busy-architect-PYVKWM4-1024x872.jpg" alt="">
            </div>

            <!-- Img_2 wrapper -->
            <div class="img_2_wrapper">
                <img src="../assets/images/businesswoman-analysing-document-P8WSNMC-1024x820.jpg" alt="">
            </div>
        </div>

        <!-- Info wrapper -->
        <div class="info_wrapper">
            <!-- Info e button -->
            <div class="info">
                <h3 class="title">
                    learn more about <br>
                    our <span>missions</span>
                </h3>
                <!-- Linea -->
                <div class="line"></div>
                <!-- Descrizione -->
                <p class="description">
                    Far far away, behind work mountains, far from the countries Vokalia and <br>
                    Consonantia, there live the blind text. Separated they live in Bookmarksgrove <br>
                    right at the coast of the Semantics, a large language ocean. Separated they live <br>
                    in Bookmarksgrove.
                </p>
                <!-- Button -->
                <button class="btn_readmore">
                    <a href="#">Read More</a>
                </button>
            </div>
        </div>
        
    </section>

</template>



<script>
export default {
    name: "Section_3"    
}
</script>



<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.section_3 {
    background-color: $bkg-color-gray-light;
    padding: 202px 0;
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 90px;

    .img_wrapper {
        flex-basis: calc((100% / 12) * 6);
        flex-grow: 1;
        position: relative;

        .img_1_wrapper {
            max-width: 626px;
            border-top-right-radius: 31px;
            overflow: hidden;
            position: relative;
    
            &::after {
                content: '';
                display: block;
                position: absolute;
                top: 0;
                left: 0;
                right: 0;
                bottom: 0;
                background-image: $bkg-color-gradient-green;
                opacity: 0.85;
            }
        }
    
        .img_2_wrapper {
            max-width: 662px;
            border-radius: 31px;
            overflow: hidden;
            position: absolute;
            top: 77px;
            left: 88px;
        }
    }

    .info_wrapper {
        flex-basis: calc((100% / 12) * 6 - 90px);
        flex-grow: 1;

        .info {

            .title {
                color: $text-color-gray-dark;
                font-size: 55px;
                font-weight: 600;

                span {
                    color: $color-green;
                }
            }

            .line {
                margin-top: 33px;
                margin-bottom: 32px;

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

            p {
                color: $text-color-gray-dark;
                margin-bottom: 38px;
                font-size: 16px;
            }

            .btn_readmore {
                border: none;
                padding: 20px 45px;
                border-radius: 31px;
                cursor: pointer;
                background-image: $bkg-color-gradient-green;
                color: $text-color-white;
                text-transform: uppercase;
                filter: drop-shadow(8px 5px 8px rgba($color: $color-green, $alpha: 0.6));
            }
        }
    }

}

</style>