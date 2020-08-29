<script>
	import Intro from "../components/sections/Intro.svelte"
	import ProjectCard from "../components/ProjectCard.svelte"
	import Section from "../components/Section.svelte"
	import ProjectsGrid from "../components/ProjectsGrid.svelte"

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

</script>

<svelte:head>
	<title>Home | Abdullah Ibne Atiq</title>
</svelte:head>

<Intro {...intro}>
	<ProjectCard compact {...projects[0]} />
</Intro>

<Section>
	<h1 style="margin-bottom: 1rem">Featured projects</h1>
	<ProjectsGrid {projects} />
</Section>