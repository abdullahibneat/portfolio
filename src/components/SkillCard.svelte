<script>
    export let name = ""
    export let description = ""
    export let urlLabel = ""
    export let url = "#"
</script>

<div class={$$props.class} style={$$props.style}>
    <h2>{name}</h2>
    <p>{description}</p>
    <a href={url}>{urlLabel}</a>
</div>

<style lang="scss">
    div {
        padding: 2rem 1rem 1rem;
        border-radius: .75rem;
        text-align: center;
        background-image: var(--linear-gradient);
        color: white;
        box-shadow: var(--box-shadow);
        transition: all 250ms ease;

        h2 {
            font-size: 1rem;
        }

        a {
            text-decoration: none;
            color: white;
            font-size: .8rem;
            float: right;
        }

        & > *:not(:last-child) {
            margin-bottom: 1rem;
        }

        &:hover {
            box-shadow: var(--box-shadow-hover-large);
            transform: scale(1.01);
        }
    }
</style>