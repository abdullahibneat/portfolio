<script>
    export let title
    export let fullWidth = false
</script>

<section title class:fullWidth class={$$props.class} style={$$props.style}>
    {#if title}<h1>{title}</h1>{/if}
    <slot />
</section>

<style lang="scss">
    section {
        padding: 3rem 0;
        margin: 0 auto;
        width: 100%;
        max-width: 80rem;

        h1 {
            margin-bottom: 1rem;
        }

        &.fullWidth h1 {
            text-align: center;
            margin-bottom: 2rem;
        }

        &:not(.fullWidth) {
            width: 90%;
            padding-left: 1.5rem;
            padding-right: 1.5rem;

            @media only screen and (min-width: 990px) {
                width: 80%;
            }
        }
    }
</style>