<template>
    <a :href="link">
        <button type="button" :class="btnStyle">
            {{name}}
        </button>
    </a>
</template>

<style lang="scss">
    button {
        padding: 15px 65px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
    }
</style>

<script>
    export default {
        name: 'Button',
        props: [
                "name",
                "link",
                "btnStyle"
        ]
    }
</script>