<template>
    <div class="circle-cursor" 
         :class="{ 'circle-cursor--hide': !customCursorShow, 
         'circle-cursor--lg': cursorGrow, 'circle-cursor--sm': cursorShrink,  }"
         :style="{ 'top': posY + 'px', 'left': posX + 'px'}"
      >
      </div>
</template>

<script>
    export default {
        name: 'CustomCursor',
        data() {
            return {
                customCursorShow: false,
                cursorGrow: false,
                cursorShrink: true,
                posY: 0,
                posX: 0,
                offsetX: 40,
                offsetY: 40
            }
        },
        methods: {
            onMouseMove(e) {
                //console.log(this.posY, this.posX)
                this.posY = e.pageY - this.offsetY;
                this.posX = e.pageX - this.offsetX;
            },
            onMouseEnter() {
                //console.log('mouse enter');
                this.customCursorShow = true;
                //this.$el.addEventListener('mousemove', this.onMouseMove, false);
            },
            onMouseLeave() {
                //console.log('mouse leave');
                this.customCursorShow = false;
                //this.$el.addEventListener('mousemove', this.onMouseLeave, true);
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
        mix-blend-mode: overlay;
        width: 80px;
        height: 80px;
        border: 4px solid var(--accent-quat);
        border-radius: 50%;
        background-color: #fff;
        z-index: 1000;
        transition: transform 200ms ease;
        display: block;
    }

    .circle-cursor--hide {
       display: none;
    }

    .circle-cursor--lg {
        mix-blend-mode: difference;
        border: 2px solid var(--light);
        transform: scale(3);
    }

    .circle-cursor--sm {
        transform: scale(.5);
    }

</style>