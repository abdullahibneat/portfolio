<script>
    let showLinks = false
    const toggleLinks = () => showLinks = !showLinks
</script>

<nav>
    <div class="logo">LOGO HERE</div>

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
        align-items: center;
        width: 80%;
        max-width: 80rem;
        padding: 3rem 1.5rem;
        margin: 0 auto;
    }

    .logo {
        color: var(--primary);
        font-weight: bold;
    }

    .menu-icon {
        z-index: 1;
        cursor: pointer;
        user-select: none;
        font-size: 1.5rem;
    }

    #links {
        display: none;
    }

    :global(a) {
        text-decoration: none;
    }

    :global(#links.show) {
        position: absolute;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: var(--primary);
        top: 0; right: 0; bottom: 0; left: 0;
    }

    :global(#links > a:not(:last-child)) {
        margin-bottom: 1rem;
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

        :global(#links > a:not(:last-child)) {
            margin-bottom: 0;
            margin-right: 1rem;
        }
    }
</style>