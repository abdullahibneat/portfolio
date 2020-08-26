<script>
    import Section from "../Section.svelte"
</script>

<Section class="intro">
    <slot/>
</Section>

<style lang="scss">
    :global(.intro) {
        display: flex;

        & > :global(div) {
            flex: 1;
            padding: 2rem;
        }

        :global(h1) {
            font-size: 2.5rem;
        }

        :global(p) {
            font-size: 1.5rem;
        }
    }
</style>