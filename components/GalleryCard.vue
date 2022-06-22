<template>
    <nuxt-link :to="link">
        <figure 
            @mouseenter="$refs.customCursor.onMouseEnter()" 
            @mouseleave="$refs.customCursor.onMouseLeave()"
            @mousemove="e => $refs.customCursor.onMouseMove(e)"
            class="gallery-card"
        >
        <div class="gallery-card--wrap">
            <div class="img-container">
                <img :src="img" :alt="title"/>
            </div>
            <figcaption>
                <h4>{{title}}</h4>
                <p>{{info}}</p>
            </figcaption>
        </div>
            <CustomCursor ref="customCursor" />
        </figure>
    </nuxt-link>
</template>

<script>
    import CustomCursor from './CustomCursor' 
    export default {
        name: 'GalleryCard',
        props: [
                "id",
                "title",
                "info",
                "img",
                "link",
        ],
        components: {
            CustomCursor
        },
    }
</script>

<style lang="scss">

figure {
    cursor: crosshair;
    margin: 0;

    .gallery-card--wrap {
        position: relative;
        overflow: hidden;
        
        .img-container {
            top: 0;
            left: 0;
            width: auto;
            height: 450px;
            overflow: hidden;

            img {
                object-fit: cover;
                width: 100%;
                height: 100%;
                transform: scale(1);
                transition: 0.5s all ease-out;
            }
        }
        
        &:hover {
            img {
                transform: scale(2);
            }
            figcaption {
                transform: translate3d(0, 0, 0);
                opacity: 1;
            }
        }

        figcaption {
            position: absolute;
            bottom: 0;
            left: 0;
            margin: 0;
            background: rgb(255,255,255);
            background: linear-gradient
                        (180deg, rgba(255,235,235,0.93) 0%, 
                        rgba(255,255,255,1) 100%);
            color: var(--dark);
            border-radius: 0 50px 0 0;
            width: 80%;
            height: 35%;
            padding: 10px 20px;
            transition: 0.5s all ease-out;
            transform: translate3d(0, 100px, 0);
            opacity: 0;

            h4 {
                font-size: 24px;
                margin-bottom: 0;
                margin-top: 18px;
            }

            p {
                font-size: 17px;
                margin-top: 3px;
            }

        }
    }
}


</style>