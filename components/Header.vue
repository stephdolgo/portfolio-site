<template>
    <header id="home"
        @mouseenter="$refs.customCursor.onMouseEnter()" 
        @mouseleave="$refs.customCursor.onMouseLeave()"
        @mousemove="e => $refs.customCursor.onMouseMove(e)"
        class="hero grid-container">
        <HeroImg />
        <div class="grid-inner">
            <div class="hero-content">
                <h1>Hi, I'm <span class="hero-content--highlighter"> Stephania</span>.</h1>
                <p>Graphic Designer and Aspiring Web Developer working remotely.</p>
                <Button 
                        v-for="Button in Buttons" 
                        :key="Button.key"
                        :name="Button.name"
                        :link="Button.link"
                        :btnStyle="Button.btnStyle"
                />
            </div>
        </div>
        <div class="grid-col--end">
            <div class="icon--scroll-down">
                <a :href="anchorLink" 
                @mouseover="$refs.customCursor.growMouse()" 
                @mouseout="$refs.customCursor.shrinkMouse()">
                <img src="/icons/arrow.svg" alt="scroll down arrow">
                </a>
            </div>
        </div>
        <CustomCursor ref="customCursor" />
    </header>
</template>

<script>
    import Button from './Button'
    import HeroImg from './HeroImg' 
    import CustomCursor from './CustomCursor'    

    export default {
        name: 'Header',
        props: [
            "anchorLink"
        ],
        components: {
            Button,
            HeroImg,
            CustomCursor
        },
        data() {
            return {
                Buttons: [
                    {key: 1, name:'Resume', link:'./resume.pdf', btnStyle:'dark-btn'},
                    {key: 2, name:'Contact', link:'mailto:stephdolgo@gmail.com?subject=Inquiry:', btnStyle:'pink-btn'},
                ],
            }
        },
    }
</script>

<style lang="scss">

    .hero {
        overflow: hidden;
        background-color: var(--purple);
        min-width: 100vw;
        max-height: 100vh;

        .hero-content {
            position: absolute;
            top: 50%;
            color: var(--white);
            z-index: 5;

            .hero-content--highlighter {
                background: linear-gradient(to top, var(--hot-pink) 10%, transparent 0%);
            }

        }

        .icon--scroll-down {
            position: absolute;
            cursor: pointer;
            bottom: 0px;
            padding-bottom: 35px;
        }
    } 

</style>