<script>
import ProjectCard from "./ProjectCard.svelte";

    export let projects = []
    export let horizontalScroll = false
</script>

<div class="container" class:horizontalScroll>
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

    .horizontalScroll {
        width: 100%;
        flex-wrap: nowrap;
        overflow-x: auto;
        padding-bottom: 2rem;

        :global(.project) {
            flex: 0 0 100%;
            position: relative;

            &:first-of-type {
                margin-left: 7rem;
            }

            // margin-right does not work for last element, use absolute positioning
            &:last-of-type:after {
                content: "";
                display: block;
                position: absolute;
                height: 20px;
                width: 7rem;
                right: -7rem;
            }

            @media only screen and (min-width: 600px) {
                flex: 0 0 50%;
            }
        }
    }
</style>