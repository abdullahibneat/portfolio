<script>
    let showLinks = false
    const toggleLinks = () => showLinks = !showLinks
</script>

<nav>
    <div>LOGO HERE</div>

    <span class="menu-icon" on:click={toggleLinks}>
        {showLinks? "✕" : "☰"}
    </span>

    <div id="links" class={showLinks? "show" : ""}>
        <a href="/">Home</a>
    </div>
</nav>

<style>
    nav {
        display: flex;
        justify-content: space-between;
        width: 80%;
        max-width: 80rem;
        padding: 3rem 1.5rem;
        margin: 0 auto;
    }

    .menu-icon {
        z-index: 1;
        cursor: pointer;
        user-select: none;
    }

    #links {
        display: none;
    }

    :global(#links.show) {
        position: absolute;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: white;
        top: 0; right: 0; bottom: 0; left: 0;
    }
    
    @media only screen and (min-width: 990px) {
        .menu-icon {
            display: none;
        }

        #links {
            display: block;
        }

        :global(#links.show) {
            position: initial;
            background: none;
        }
    }
</style>