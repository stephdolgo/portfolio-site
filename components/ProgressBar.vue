<template>
    <div id="progress-bar">
        <div class="timeMarker">{{ timeText }}</div>
        <div class="progress-container">
            <div class="scroll">
                <span class="scroll-progress" :style="{ 'height': progress + '%' }">
                </span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ProgressBar',
        data() {
            return {
                timeText: '',
                progress: 0
            }
        },
        methods: {
            timeOfDay() {
                const time = new Date().getHours();
                console.log(time);

                if (time >= 0 && time < 3) {
                    return 'hoot! welcome night owl';
                } else if (time == 3) {
                    return 'wah wah wa-wah wa';
                } else if (time > 3 && time <= 8) {
                    return 'the early bird gets the worm';
                } else if (time > 8 && time <= 10) {
                    return 'good mornin\' to you'
                } else if (time === 11) {
                    return 'time for elevenses';
                } else if (time === 12 || time !== 13 && time !== 15 && time >= 14 && time <= 18) {
                    return 'good afternoon';
                } else if (time === 13) {
                    return 'what did you have for lunch?';
                } else if (time === 15) {
                    return 'time for afternoon tea';
                } else if (time >= 19 && time < 22) {
                    return 'good evening';
                } else if (time === 22 || time === 23) {
                    return 'mr.sandman bring me a dream';
                } else {
                    return '';
                }
            },
            updateProgress() {
                const { documentElement, body } = document;
                let windowScroll = body.scrollTop || documentElement.scrollTop;
                let height = documentElement.scrollHeight - documentElement.clientHeight;
                this.progress = (windowScroll / height) * 100;
            }
        },
        mounted() {
            this.timeText = this.timeOfDay();
            window.addEventListener("scroll", this.updateProgress);
        }
    }
</script>

<style lang="scss">
    #progress-bar {
        position: relative;
        opacity: 0.65;
        transition: all 0.25s ease;
        cursor: none;
        z-index: 3000;

        &:hover {
            opacity: 1;
        }
    }
    .progress-container {
        position: fixed;
        right: 0;
        top: 40%;
        margin-right: 25px;

        .scroll {
            position: relative;
            width: 5px;
            height: 270px;
            background-color: var(--accent-secondary);

            .scroll-progress {
                position: absolute;
                display: block;
                width: 100%;
                overflow: none;
                background-color: var(--accent-tert);
            }
        }
    }

    .timeMarker {
        font-weight: 700;
        margin-right: 35px;
        position: fixed;
        right: 0;
        top: 40%;
        color: var(--accent-tert);
        writing-mode: vertical-lr;
    }
</style>