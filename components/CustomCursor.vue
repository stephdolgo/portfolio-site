<template>
    <div class="circle-cursor" 
         :class="{ 'circle-cursor--hide': !customCursorShow, 
         'circle-cursor--lg': cursorGrow, 'circle-cursor--sm': cursorShrink   }"
         :style="{ 'top': posY + 'px', 'left': posX + 'px'}"
      >
      </div>
</template>

<script>
    export default {
        name: 'CustomCursor',
        async mounted() {
            await this.$nextTick();          
        },
        data() {
            return {
                customCursorShow: false,
                cursorGrow: false,
                cursorShrink: true,
                posY: 0,
                posX: 0,
                offset: 15
            }
        },
        destroyed() {
                
        },
        methods: {
            onMouseMove(e) {
                //console.log(this.posY, this.posX)
                this.posY = e.clientY - this.offset;
                this.posX = e.clientX - this.offset;
            },
            onMouseEnter() {
                //console.log('mouse enter');
                console.log(this.customCursorShow);
                this.customCursorShow = true;
                this.$el.addEventListener('mousemove', this.onMouseMove, false);
            },
            onMouseLeave() {
                //console.log('mouse leave');
                console.log(this.customCursorShow);
                this.customCursorShow = false;
                this.$el.addEventListener('mousemove', this.onMouseLeave, false);
            },
            growMouse() {
                this.cursorGrow = true;
                this.cursorShrink = false;
            },
            shrinkMouse() {
                this.cursorGrow = false;
                this.cursorShrink = true;
            }
        } 
    }
</script>

<style lang="scss">

    .circle-cursor {
        position: absolute;
        top: 0;
        left: 0;
        pointer-events: none;
        mix-blend-mode: difference;
        width: 60px;
        height: 60px;
        border-radius: 50%;
        background-color: white;
        z-index: 1000;
        transition: transform 200ms ease;
        display: block;
    }

    .circle-cursor--hide {
       display: none;
    }

    .circle-cursor--lg {
        transform: scale(3);
    }

    .circle-cursor--sm {
        transform: scale(.5);
    }

</style>