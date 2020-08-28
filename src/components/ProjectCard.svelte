<script>
    export let featuredImage = "https://via.placeholder.com/1280x720?text=Featured+Image"
    export let title = ""
    export let summary = ""
    export let repoURL = ""
    export let projectURL = ""
    export let compact = false
</script>

<div class={$$props.class} class:wrapper={!compact}>
    <div class="container" class:compact>
        <img src={featuredImage} alt={title}>
        <div class="content">
            <h2>{title}</h2>
            <p>{summary}</p>
            <div class="links">
                {#if repoURL}<a href={repoURL}>GitHub →</a>{/if}
                {#if projectURL}<a href={projectURL}>Read More →</a>{/if}
            </div>
        </div>
    </div>
</div>

<style lang="scss">
    .wrapper {
        padding: 1rem;
    }

    .container {
        display: flex;
        flex-direction: column;

        img {
            border-radius: .75rem .75rem 0 0;
        }

        .content {
            width: 100%;
            padding: 2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: flex-start;
            background-image: var(--linear-gradient);
            border-radius: 0 0 .75rem .75rem;

            p {
                font-size: 1rem;
            }

            &, a {
                color: white;
            }
            
            .links {
                display: flex;
                justify-content: space-between;
                width: 100%;
                font-size: 0.8rem;
            }

            & > *:not(:last-child) {
                margin-bottom: 1rem;
            }
        }

        &.compact {
            position: relative;

            img {
                width: 100%;
                border-radius: .75rem;
            }

            .content {
                position: absolute;
                top: 0; right: 0; bottom: 0; left: 0;
                border-radius: .75rem;
                background-image: var(--linear-gradient);
                justify-content: space-between;
                align-items: center;
                height: 100%;
                min-height: fit-content;
                opacity: 0;
                transition: opacity 250ms ease;
            }

            &:hover .content {
                opacity: 1;
            }
        }
    }
</style>