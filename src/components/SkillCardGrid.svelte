<script>
    import SkillCard from "./SkillCard.svelte"
    export let skills = []
</script>

<div class={$$props.class} style={$$props.style}>
    {#each skills as skill}
        <div class="skill">
            <SkillCard {...skill} />
        </div>
    {/each}
</div>

<style lang="scss">
    div {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        
        .skill {
            flex: 50%;
            padding: .5rem;
            max-width: 15rem;
            align-items: flex-start;

            @media only screen and (min-width: 990px) {
                &:nth-child(2n) {
                    padding-top: 3rem;
                    align-items: flex-end;
                }
            }
        }
    }
</style>