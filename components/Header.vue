<template>
    <header id="home" 
        @mouseenter="$refs.customCursor.onMouseEnter()" 
        @mouseleave="$refs.customCursor.onMouseLeave()"
        @mousemove="e => $refs.customCursor.onMouseMove(e)"
        class="hero grid-container"
    >
        <HeroImg />
        <div class="grid-inner">
            <div class="hero-content">
                <h1>Hi, I'm <span class="hero-content--highlighter"> Stephania</span>.</h1>
                <p>Graphic Designer and self-taught web developer working remotely.</p>
                <a href="./resume.pdf">
                    <Button btnStyle="dark-btn">Resume</Button>
                </a>
                <a href="mailto:stephdolgo@gmail.com?subject=Inquiry:">
                    <Button btnStyle="primary-btn">Contact</Button>
                </a>
            </div>
        </div>
        <div class="grid-col--end">
            <div class="icon--scroll-down">
                <a :href="anchorLink" 
                    @mouseover="$refs.customCursor.growMouse()" 
                    @mouseout="$refs.customCursor.shrinkMouse()"
                >
                <img src="/icons/arrow.svg" alt="scroll down arrow">
                </a>
            </div>
        </div>
        <CustomCursor ref="customCursor" />
    </header>
</template>

<script> 
    export default {
        name: 'Header',
        props: [
            "anchorLink"
        ]
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
            top: 40%;
            color: var(--white);
            z-index: 5;
            margin-left: 20px;

            .hero-content--highlighter {
                background: linear-gradient(to top, var(--accent-tert) 10%, transparent 0%);
            }

            h1 {
                font-size: 4em;
                margin-bottom: 0;
            }

            p {
                font-size: 1.35em;
                color: var(--accent-primary);
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