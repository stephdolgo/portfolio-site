<template>
    <nav :class="{ 'nav-hide': !navShow }">
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#projects">Design</a></li>
            <li>Art</li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
</template>

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
        box-shadow: 0px 3px 2px rgba(0, 0, 0, 0.068) ;
        transition: 0.5s all ease-out;

        ul li {
            display: inline;
            font-size: 1rem;
            padding: 1em 3em;
        }

        a {
            text-transform: uppercase;
            font-weight: 700;
            transition: 0.5s all ease-out;
        }

        &:hover,
        &:focus {
            opacity: 1;
            background-color: var(--accent-quin);
            color: var(--light); 
            a {
                color: var(--dark);
                opacity: 0.5;
            }
            a:hover,
            a:focus {
                color: var(--accent-quat);
                opacity: 1;
            }
        }
    }

    .nav-hide {
        transform: translate3d(0, -100%, 0);
    }

</style>