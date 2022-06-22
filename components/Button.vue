<template>
    <button type="button" :class="btnStyle">
        <slot /> 
    </button>
</template>

<script>
    export default {
        name: 'Button',
        props: [
            "btnStyle"
        ]
    }
</script>

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
    
    .primary-btn {
        color: var(--dark);
        background-color: var(--accent-primary);
        border: none;
        border-radius: 15px;
        transition: 0.5s ease;
        &:hover,
        &:focus {
            box-shadow: inset 15em 0 0 0 var(--accent-secondary);
        }
    }

    .dark-btn {
        color: var(--light);
        background-color: var(--dark);
        border: 2px soild var(--light);
        border-radius: 15px;
        transition: 0.5s ease;
        &:hover,
        &:focus {
            box-shadow: inset 15em 0 0 0 var(--accent-secondary);
            color: var(--dark);
        }
    }

    .light-btn {
        color: var(--dark);
        background-color: var(--light);
        border: 2px soild var(--dark);
        border-radius: 15px;
    }
</style>