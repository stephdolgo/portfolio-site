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
            height: 400px;
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
        }

        figcaption {
            position: absolute;
            margin: 10px 20px;
            bottom: 0;
            left: 0;
        }
    }
}


</style>