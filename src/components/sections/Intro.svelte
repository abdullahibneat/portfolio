<script>
    import Section from "../Section.svelte"
</script>

<Section class="intro">
    <slot/>
</Section>

<style lang="scss">
    :global(.intro) {
        display: flex;
        flex-direction: column;
        text-align: center;

        & > :global(div) {
            flex: 1;
            padding: 2rem;

            & > :global(*:not(:last-child)) {
                margin-bottom: 1rem;
            }
        }

        :global(h1) {
            font-size: 2.5rem;
        }

        :global(p) {
            font-size: 1.5rem;
        }

        @media only screen and (min-width: 990px) {
            flex-direction: row;
            text-align: initial;
        }
    }
</style>