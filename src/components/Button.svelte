<script>
    export let label = ""
    export let onClick = () => {}
</script>

<button class={$$props.class} on:click={onClick}>{label}</button>

<style lang="scss">
    button {
        outline: none;
        padding: .5rem 1rem;
        border: none;
        border-radius: .75rem;
        background: black;
        color: white;
        box-shadow: var(--box-shadow);
        transition: transform 250ms ease;
        font-weight: bold;

        &:hover {
            transform: scale(1.05);
        }
    }
</style>