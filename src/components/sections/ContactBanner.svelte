<script>
import Button from "../Button.svelte"
    import Section from "../Section.svelte"

    export let heading = "Get in touch."
</script>

<Section class="contact">
    <div>
        <h1>{heading}</h1>
        <p>Do you have a project in mind? Or need help in your company? If so, feel free to contact me.</p>
    </div>
    <div>
        <a href="#"><Button class="button" label="Let's talk →"/></a>
    </div>
</Section>

<style lang="scss">
    :global(.contact) {
        max-width: 60rem !important;

        div {
            h1 {
                font-size: 3rem;
            }

            p {
                font-size: 1.5rem;
                margin: 1rem 0;
            }

            :global(.button) {
                font-size: 1.5rem;
                float: right;
            }
        }

        @media only screen and (min-width: 600px) {
            display: flex;
            align-items: flex-end;

            div {
                p {
                    margin-bottom: 0;
                }

                &:first-of-type {
                    flex: 2;
                    margin-right: 2rem;
                }
            }
        }
    }
</style>