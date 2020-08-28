<script>
import ProjectCard from "./ProjectCard.svelte";

    export let projects = []
</script>

<div class="container">
    {#each projects as project }
        <ProjectCard class="project" {...project} />
    {/each}
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
</style>