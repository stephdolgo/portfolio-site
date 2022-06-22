<template>
    <section id="contact" class="grid-container padding">
        <div class="grid-inner">
            <h2 class="display-font">
                Let's make memorable experiences together.
            </h2>
            <ul>
                <li><a a href="mailto:stephdolgo@gmail.com?subject=Inquiry:" class="underline-link">Say Hello</a></li>
                <li><a href="./docs/resume.pdf" class="underline-link">View Resume</a></li>
            </ul>
        </div>  
    </section>
</template>

<script>
    export default {
        name: 'Contact'
    }
</script>

<style lang="scss">
    #contact {
        width: 100%;
        background-color: var(--contact);
        text-align: center;
        grid-row: auto;
        align-self: end; 
        position: sticky;

        h2 {
            font-size: 32px;
            margin: 1.25em 0;
        }

        ul {
            padding: 0;
            margin: 0;
        }
        
        ul li {
            display: inline;
            font-weight: 700;
            font-size: 18px;
            padding: 1em 3em;
        }  
    }
</style>