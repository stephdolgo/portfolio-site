<template>
    <nav :class="{ 'nav-hide': !navShow }">
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li>Design</li>
            <li>Illustrations</li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
</template>

<style lang="scss">

    nav {
        width: 100vw;
        height: 65px;
        position: fixed;
        top: 0;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        z-index: 100;
        background-color: var(--white);
        opacity: 0.9;
        transform: translate3d(0, 0, 0);
        transition: 0.5s all ease-out;

        ul li {
            display: inline;
            font-size: 1rem;
            padding: 1em 3em;
        }
    }

    .nav-hide {
        transform: translate3d(0, -100%, 0);
    }

</style>

<script>
    export default {
        name: 'Nav',
        data() {
            return {
                navShow: true,
                lastScrollY: 0,
                scrollOffset: 40
            }
        },
        mounted() {
            window.addEventListener('scroll', this.onScroll);
        },
        beforeDestroy() {
            window.removeEventListener('scroll', this.onScroll)
        },
        methods: {
            onScroll() {
                const currentScrollY = window.pageY || document.documentElement.scrollTop;
                // console.log("scroll:", window.scrollY)
                if (currentScrollY < 0) {
                    return;
                }
                if (Math.abs(currentScrollY - this.lastScrollY) < this.scrollOffset) {
                    return
                }
                this.navShow = currentScrollY < this.lastScrollY;
                this.lastScrollY = currentScrollY;
            }           
        }
    }
</script>