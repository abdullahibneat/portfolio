<script>
    import ProjectsGrid from "../components/ProjectsGrid.svelte"
    import Section from "../components/Section.svelte"
    import ContactBanner from "../components/sections/ContactBanner.svelte"

    import projects from "../../data/projects"
</script>

<Section title="Projects">
    <ProjectsGrid {projects} filtering />
</Section>

<ContactBanner />