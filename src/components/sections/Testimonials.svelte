<script>
    import Section from "../Section.svelte"
    import Testimonial from "../Testimonial.svelte"

    export let title
    export let fullWidth
    export let testimonials = []
</script>

<Section {title} {fullWidth}>
    <div class="testimonials">
        {#each testimonials as testimonial}
            <Testimonial class="testimonial" {...testimonial}/>
        {/each}
    </div>
</Section>

<style lang="scss">
    .testimonials {
        display: flex;
        flex-wrap: nowrap;
        width: 100%;
        overflow-x: auto;
        overflow-y: hidden;
        padding: 2rem 0;
        position: relative;

        :global(.testimonial) {
            flex: 0 0 100%;
        }
    }
</style>