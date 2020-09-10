<script>
	import Intro from "../components/sections/Intro.svelte"
	import ProjectCard from "../components/ProjectCard.svelte"
	import Section from "../components/Section.svelte"
	import ProjectsGrid from "../components/ProjectsGrid.svelte"
	import SkillGrid from "../components/SkillCardGrid.svelte"
	import Button from "../components/Button.svelte"
	import Testimonials from "../components/sections/Testimonials.svelte"
	import ContactBanner from "../components/sections/ContactBanner.svelte"

	const projects = [
		{
			"title": "Blog list",
			"summary": "A full stack application to save blogs, built to learn React and NodeJS. It features interacting with a MongoDB database, user authentication, testing and continuous integration through Vercel.",
			"featuredImage": "https://abdu.io/assets/media/BlogList/ft.jpg",
			"projectURL": "https://abdu.io/project/blog-application/",
			"repoURL": "https://github.com/abdullahibneat/blog-backend"
		},
		{
			"title": "Chat Room",
			"summary": "A Java peer-to-peer chatroom where people can send messages and communicate with each other",
			"featuredImage": "https://abdu.io/assets/media/ChatRoom/ft.jpg",
			"projectURL": "https://abdu.io/project/chaat-room/",
			"repoURL": "https://github.com/abdullahibneat/p2p-chat-room"
		},
		{
			"title": "PointAR",
			"summary": "My team and I identified a problem found in a number of sectors: integration. The solution? Augmented Reality, BYOD and Fujitsu Technology.",
			"featuredImage": "https://abdu.io/assets/media/PointAR/ft.jpg",
			"projectURL": "https://abdu.io/project/pointar/",
			"repoURL": "https://github.com/abdullahibneat/PointAR"
		},
		{
			"title": "PointAR",
			"summary": "My team and I identified a problem found in a number of sectors: integration. The solution? Augmented Reality, BYOD and Fujitsu Technology.",
			"featuredImage": "https://abdu.io/assets/media/PointAR/ft.jpg",
			"projectURL": "https://abdu.io/project/pointar/",
			"repoURL": "https://github.com/abdullahibneat/PointAR"
		}
	]

	const intro = {
		title: "Lorem ipsum dolor sit amet",
		text: "Consectetur adipiscing elit. Mauris in est scelerisque, scelerisque risus vel, tincidunt dolor."
	}

	const skills = [
        {
            name: "Full Stack Development",
            description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Inventore, cumque.",
            urlLabel: "See projects →",
            url: "#"
        },
        {
            name: "Backend Development",
            description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Inventore, cumque.",
            urlLabel: "See projects →",
            url: "#"
        },
        {
            name: "Databases",
            description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Inventore, cumque.",
            urlLabel: "See projects →",
            url: "#"
        },
        {
            name: "Git",
            description: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Inventore, cumque.",
            urlLabel: "See projects →",
            url: "#"
		}
	]

	const testimonials = [
		{
			text: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores quis quisquam dicta velit similique facilis nam alias saepe dolor architecto.",
			author: "John Doe"
		},
		{
			text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Incidunt mollitia accusantium nemo!",
			author: "John Doe"
		},
		{
			text: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt autem itaque velit quia sunt cum dolorum.",
			author: "John Doe"
		}
	]

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