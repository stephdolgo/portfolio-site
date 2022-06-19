<template>
    <section id="contact" class="grid-container padding">
        <div class="grid-inner">
            <h3 class="display-font">
                Let's make memorable experiences together.
            </h3>
            <ul>
                <li>Say Hello</li>
                <li>View Resume</li>
            </ul>
        </div>  
    </section>
</template>

<style lang="scss">
    #contact {
        width: 100%;
        background-color: var(--contact);
        text-align: center;
        grid-row: auto;
        align-self: end; 
        position: sticky;

        h3 {
            font-size: 20px;
        }

        ul {
            padding: 0;
            margin: 0;
        }
        
        ul li {
            display: inline;
            font-size: 1rem;
            padding: 1em 3em;
        }  
    }
</style>

<script>
    export default {
        name: 'Contact'
    }
</script>