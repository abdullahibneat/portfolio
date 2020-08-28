<script>
    export let featuredImage = "https://via.placeholder.com/1280x720?text=Featured+Image"
    export let title = ""
    export let summary = ""
    export let repoURL = ""
    export let projectURL = ""
</script>

<div class="wrapper">
    <div class="container">
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
        background-image: var(--linear-gradient);
        border-radius: .75rem;
        display: flex;

        img {
            width: 50%;
            border-radius: .75rem 0 0 .75rem;
        }

        .content {
            width: 100%;
            padding: 2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;

            &, :global(a) {
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

        @media only screen and (min-width: 990px) {
            flex-direction: column;

            img {
                width: 100%;
                border-radius: .75rem .75rem 0 0;
            }

            .content {
                align-items: flex-start;
                padding-top: 1rem;
            }
        }
    }
</style>