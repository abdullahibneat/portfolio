<script>
import ProjectCard from "./ProjectCard.svelte";

    export let projects = []
    export let horizontalScroll = false
</script>

<div class="wrapper" class:horizontalScroll>
    <div class="container">
        {#each projects as project }
            <ProjectCard class="project" {...project} />
        {/each}
    </div>
</div>

<style lang="scss">
    .container {
        display: flex;
        flex-wrap: wrap;

        :global(.project) {
            @media only screen and (min-width: 600px) {
                width: 50%;
            }

            @media only screen and (min-width: 990px) {
                width: 33.3333%;
            }
        }
    }

    .horizontalScroll {
        overflow-x: auto;

        .container {
            flex-wrap: nowrap;
            flex-direction: row;
            justify-content: center;

            // Add padding to start/end, float is necessary
            padding: 0 7rem 2rem;
            float: left;

            :global(.project) {
                min-width: 20rem;
            }
        }
    }
</style>