<script>
    import Section from "./Section.svelte";
    import { slide } from "svelte/transition"

    let width
    $: showLinks = width > 990

    const toggleLinks = () => showLinks = !showLinks
</script>

<svelte:window bind:innerWidth={width} />

<Section>
    <nav>
        <div class="logo">LOGO HERE</div>
    
        <span class="menu-icon" on:click={toggleLinks}>
            {showLinks? "✕" : "☰"}
        </span>
    
        {#if showLinks}
            <div class="links" transition:slide>
                <a href="/">Home</a>
            </div>
        {/if}
    </nav>
</Section>

<style lang="scss">
    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;

        .logo {
            color: var(--primary);
            font-weight: bold;
        }

        .menu-icon {
            z-index: 1;
            cursor: pointer;
            user-select: none;
            font-size: 1.5rem;
            position: fixed;
            right: 10%;
            color: white;
            width: 3rem;
            height: 3rem;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 50%;
            background: var(--primary);
            opacity: 0.75;
        }

        .links {
            position: fixed;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: var(--primary);
            opacity: 0.95;
            top: 0; right: 0; bottom: 0; left: 0;

            :global(a) {
                text-decoration: none;
                color: var(--dark);
                font-size: 1.5rem;
            }

            :global(a:not(:last-child)) {
                margin-bottom: 1rem;
            }
        }

        @media only screen and (min-width: 990px) {
            .menu-icon {
                display: none;
            }

            .links {
                flex-direction: row;
                position: initial;
                background: none;

                :global(a) {
                    font-size: initial;

                    &:not(:last-child) {
                        margin-bottom: 0;
                        margin-right: 1rem;
                    }
                }
            }
        }
    }
</style>