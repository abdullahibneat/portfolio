<script>
    import ProjectCard from "./ProjectCard.svelte"

    export let projects = []
    export let horizontalScroll = false
    export let filtering = false

    // Get list of all skills
    const skills = new Set(["All"])
    projects.forEach(p => {
        p.skills.forEach(s => skills.add(s))
    })

    // Dollar sign because currentFilter is reactive and can change.
    $: filterProjects = p => {
        if(filtering && currentFilter !== "All") return p.skills.includes(currentFilter)
        else return true
    }

    let currentFilter = "All"
</script>

<div class="wrapper" class:horizontalScroll>
    {#if filtering}
        <div class="filter">
            {#each [...skills] as skill}
                <span class:selected={skill === currentFilter} on:click={() => currentFilter = skill}>{skill}</span>
            {/each}
        </div>
    {/if}
    <div class="container">
        {#each projects.filter(filterProjects) as project }
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

    .filter {
        margin: 1rem;

        span {
            display: inline-block;
            margin: .5rem .25rem;
            padding: .5rem 1rem;
            border-radius: 2rem;
            border: solid 1px var(--disabled);
            color: var(--disabled);
            cursor: pointer;
            transition: all 250ms ease;

            &:not(.selected):hover {
                box-shadow: var(--box-shadow-hover);
            }

            &.selected {
                background-color: var(--primary);
                border-color: var(--primary);
                color: white;
            }

            // &:not(:last-child) {
            //     margin-right: .5rem;
            // }
        }
    }
</style>