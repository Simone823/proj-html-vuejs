<template>
    
    <!-- Sezione 5 -->
    <section class="section_5">

        <!-- Overlay -->
        <div class="overlay_black"></div>

        <!-- Info wrapper-->
        <div class="info_wrapper">
            <h4 class="virgolette">&ldquo;</h4>
            <h3 class="sottotitolo">
                When it comes to barbequing, there are two main schools of
                throught for the techniques that you can use. Freshly scrambled 
                eggs whith applewood smoked bacon - are amazing!
            </h3>

            <!-- Client -->
            <div class="client">
                <!-- Avatar -->
                <div class="avatar_client">
                    <img src="../assets/images/businesswoman-analysing-document-P8WSNMC-1024x820.jpg" alt="">
                </div>
                <!-- info client -->
                <div class="info_client">
                    <h3 class="name">Lissa Durbin</h3>
                    <h4 class="type">Client</h4>
                </div>

            </div>

        </div>

    </section>

</template>



<script>
export default {
    name: "Section_5",
}
</script>



<style lang="scss" scoped>
// Import common scss
@import "../assets/scss/common.scss";

.section_5 {
    padding: 171px 0;
    background-image: url("../assets/images/four-businesspeople-in-a-boardroom-with-paperwork-PC4V8H4.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    position: relative;

    .overlay_black {
        background-image: $bkg-color-gradient-gray-dark;
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        opacity: 0.9;
    }

    .info_wrapper {
        max-width: 50%;
        margin: 0 auto;
        text-align: center;
        z-index: 10;
        position: relative;

        .virgolette {
            color: $color-green;
            font-size: 100px;
        }

        .sottotitolo {
            line-height: 45px;
            font-size: 27px;
            font-weight: 300;
            font-style: italic;
            color: $bkg-color-gray-light;
            margin-bottom: 85px;
        }

        .client {
            margin: 0 auto;
            text-align: center;

            .avatar_client {
                width: 100px;
                height: 100px;
                border-radius: 50%;
                overflow: hidden;
                margin: 0 auto;
                margin-bottom: 31px;
                background-color: $bkg-color-white;
                display: flex;
                align-items: center;
                justify-content: center;
                
                img {
                    object-fit: cover;
                    object-position: center;
                    width: 95%;
                    height: 95%;
                    border-radius: 50%;
                    border: 1px solid $bkg-color-gray-light-shade;
                }
            }

            .info_client {

                .name {
                    color: $color-green;
                    text-transform: uppercase;
                    font-size: 24px;
                    margin-bottom: 13px;
                    font-weight: 500;
                }

                .type {
                    color: $bkg-color-gray-light;
                    font-size: 18px;
                }
            }
        }

    }
}
</style>