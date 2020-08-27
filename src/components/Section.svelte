<section class={$$props.class}>
    <slot />
</section>

<style lang="scss">
    section {
        width: 90%;
        max-width: 80rem;
        padding: 3rem 1.5rem;
        margin: 0 auto;

        @media only screen and (min-width: 990px) {
            width: 80%;
        }
    }
</style>