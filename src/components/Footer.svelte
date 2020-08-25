<script>
    import Section from "./Section.svelte";
</script>

<Section>
    <footer>
        <p>&copy; 2016 - {new Date().getFullYear()} Abdullah Ibne Atiq</p>
    </footer>
</Section>

<style>
    footer {
        font-size: 0.9rem;
        text-align: center;
    }

    @media only screen and (min-width: 990px) {
        footer {
            text-align: initial;
        }
    }
</style>