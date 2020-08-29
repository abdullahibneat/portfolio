<script>
    import Section from "../Section.svelte"
    export let title
    export let text
</script>

<Section class="intro">
    <div>
        <h1>{title}</h1>
        <p>{text}</p>
    </div>
    <div>
        <slot/>
    </div>
</Section>

<style lang="scss">
    div {
        flex: 1;
        text-align: center;

        h1 {
            font-size: 2.5rem;
        }

        p {
            font-size: 1.5rem;
        }

        &:first-of-type {
            padding: 3rem 1rem;
        }

        & > *:not(:last-child) {
            margin-bottom: 1rem;
        }
    }

    :global(.intro) {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        @media only screen and (min-width: 990px) {
            flex-direction: row;

            div {
                padding: 1rem;
                text-align: initial;
            }
        }
    }
</style>