<script>
    export let fullWidth = false
</script>

<section class:fullWidth class={$$props.class} style={$$props.style}>
    <slot />
</section>

<style lang="scss">
    section {
        padding: 3rem 0;
        margin: 0 auto;
        width: 100%;
        max-width: 80rem;

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