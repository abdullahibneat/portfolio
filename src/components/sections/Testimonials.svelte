<script>
    import Section from "../Section.svelte"
    import Testimonial from "../Testimonial.svelte"

    export let title
    export let fullWidth
    export let testimonials = []
</script>

<Section {title} {fullWidth}>
    <div class="testimonials">
        {#each testimonials as testimonial, i}
            <Testimonial class="testimonial" id={`testimonial-${i}`} {...testimonial}/>
        {/each}
    </div>
    <div class="circles">
        {#each { length: testimonials.length } as _, i}
            <a href={`#testimonial-${i}`} />
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
        position: relative;
        scroll-snap-type: x mandatory;
        scroll-behavior: smooth;

        :global(.testimonial) {
            padding-top: 1rem;
            flex: 0 0 100%;
            scroll-snap-align: start;
        }
    }

    .circles {
        display: flex;
        justify-content: center;
        margin-top: 1rem;

        a {
            display: block;
            width: .75rem;
            height: .75rem;
            border-radius: 50%;
            background-color: #333;

            &:not(:last-child) {
                margin-right: .75rem;
            }
        }
    }
</style>