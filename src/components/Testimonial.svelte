<script>
    export let text = ""
    export let author = ""
</script>

<div class={$$props.class} style={$$props.style}>
    <blockquote>{text}</blockquote>
    <cite>{author}</cite>
</div>

<style lang="scss">
    div {
        text-align: center;
    }

    blockquote {
        font-size: 2rem;
        width: 80%;
        margin: 0 auto;
        position: relative;

        // Quote marks
        &:before, &:after {
            position: absolute;
            font-size: 7rem;
            font-weight: bold;
            color: var(--primary);
        }

        &:before {
            content: "“";
            top: -3rem;
            left: -4rem;
        }

        &:after {
            content: "”";
            bottom: -5rem;
            right: -5rem;
        }
    }

    cite {
        display: block;
        margin-top: 1rem;
    }
</style>