<script>
	import Intro from "../components/sections/Intro.svelte"
	import ProjectCard from "../components/ProjectCard.svelte"
	import Section from "../components/Section.svelte"
	import ProjectsGrid from "../components/ProjectsGrid.svelte"
	import SkillGrid from "../components/SkillCardGrid.svelte"
	import Button from "../components/Button.svelte"
	import Testimonials from "../components/sections/Testimonials.svelte"
	import ContactBanner from "../components/sections/ContactBanner.svelte"

	import projects from "../../data/projects"
	import skills from "../../data/skills"
	import testimonials from "../../data/testimonials"

	const intro = {
		title: "Lorem ipsum dolor sit amet",
		text: "Consectetur adipiscing elit. Mauris in est scelerisque, scelerisque risus vel, tincidunt dolor."
	}
</script>

<svelte:head>
	<title>Home | Abdullah Ibne Atiq</title>
</svelte:head>

<Intro {...intro}>
	<ProjectCard compact {...projects[0]} />
</Intro>

<Section title="Featured projects" fullWidth>
	<ProjectsGrid {projects} horizontalScroll />
</Section>

<Section class="skillsSection" style="display: flex;">
	<SkillGrid class="skillsGrid" {skills}/>
	<div>
		<h1>What I do</h1>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores explicabo itaque obcaecati molestiae dolorem vitae corporis? Magni, nesciunt? Exercitationem ipsum cupiditate ducimus voluptatem, voluptas sint.</p>
		<a href="#"><Button label="View all projects →" /></a>
	</div>
</Section>

<Testimonials {testimonials}/>

<ContactBanner />

<style lang="scss">
	:global(.skillsSection) {
		display: flex;
		flex-direction: column-reverse;
		justify-content: center;
		align-items: center;

		div {
			padding: 2rem;

			p {
				margin: 1rem 0;
			}
		}

		@media only screen and (min-width: 990px) {
			flex-direction: row;

			:global(.skillsGrid) {
				flex: 3;
			}

			div {
				flex: 2;
			}
		}
	}
</style>