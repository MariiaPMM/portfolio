<template>
	<main class="container">
		<section class="hero">
			<h1>{{ name }}</h1>
			<p>{{ title }}</p>
			<div class="links">
				<a
					:href="github"
					target="_blank"
					class="btn"
					>GitHub</a
				>
				<a
					:href="cv"
					target="_blank"
					class="btn"
					>Моє CV</a
				>
				<a
					:href="cr"
					target="_blank"
					class="btn"
					>Сертифікат</a
				>
				<a
					href="https://www.linkedin.com/in/mariia-pastukh-b34879326"
					target="_blank"
					class="btn"
					>LinkedIn</a
				>
			</div>
		</section>

		<section class="projects">
			<h2>Проєкти</h2>
			<div
				class="project"
				v-for="project in projects"
				:key="project.name"
			>
				<h3>{{ project.name }}</h3>
				<p>{{ project.description }}</p>
				<a
					:href="project.link"
					target="_blank"
					class="project-link"
					>Переглянути</a
				>
			</div>
		</section>

		<section class="contact">
			<h2>Контакти</h2>
			<p>
				Email: <a :href="`mailto:${email}`">{{ email }}</a>
			</p>
		</section>
	</main>
</template>

<script>
import cvFile from '@/assets/my-cv.pdf';
import crFile from '@/assets/cr.pdf';
export default {
	name: 'HomeView',
	data() {
		return {
			name: 'Pastukh Mariia',
			title:
				'Frontend Developer | Vue.js | JavaScript | CSS, SASS | HTML | BEM | Pinia | Vue Router | GitHub | Git | REST API',
			github: 'https://github.com/MariiaPMM',
			cv: cvFile,
			cr: crFile,
			email: 'mahka230@gmail.com',
			projects: [
				{
					name: 'Test Task',
					description: 'Сайт для тестового завдання з адаптивним дизайном.',
					link: 'https://mariiapmm.github.io/test-task/',
				},
				{
					name: 'Concert Booking App (в розробці)',
					description:
						'Проєкт з бронювання квитків. Реалізовано з використанням Vue, Express та MySQL.',
					link: 'https://github.com/MariiaPMM/concert1',
				},
			],
		};
	},
};
</script>

<style scoped>
html,
body,
#app {
	height: 100vh;
	width: 100vw;
	margin: 0;
	padding: 0;
	color: #cfd8dc;
	font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
	display: flex;
	justify-content: center;
	align-items: center;
	overflow: hidden;
}

.container {
	max-width: 800px;
	width: 90vw;
	padding: 1.5rem 2rem;
	background: #1e2228;
	border-radius: 10px;
	box-shadow: 0 6px 18px rgba(0, 0, 0, 0.6);
	display: flex;
	flex-direction: column;
	justify-content: center;
	text-align: center;
}

.hero h1 {
	color: aliceblue;
}

.hero p {
	font-size: 1rem;
	color: #b0bec5;
	margin-bottom: 1rem;
	font-weight: 500;
	line-height: 1.3;
}

.links {
	display: flex;
	justify-content: center;
	gap: 0.8rem;
	flex-wrap: wrap;
	margin-bottom: 2rem;
}

.links a.btn {
	display: inline-block;
	padding: 0.4rem 1.2rem;
	border-radius: 20px;
	background-color: #3949ab;
	color: #e3f2fd;
	text-decoration: none;
	font-weight: 600;
	font-size: 0.85rem;
	transition: background-color 0.3s ease, box-shadow 0.3s ease;
	box-shadow: 0 1.5px 5px rgba(57, 73, 171, 0.6);
}

.links a.btn:hover {
	background-color: #283593;
	box-shadow: 0 4px 12px rgba(40, 53, 147, 0.8);
}

.projects {
	width: 100%;
	margin-top: 0;
}

.projects h2 {
	font-size: 1.6rem;
	margin-bottom: 1.2rem;
	color: #90caf9;
	border-bottom: 2px solid #3949ab;
	padding-bottom: 0.4rem;
	text-align: center;
	font-weight: 600;
}

.project {
	margin-bottom: 1.2rem;
	background: #2c323c;
	padding: 0.8rem 1.2rem;
	border-radius: 8px;
	box-shadow: 0 1.5px 8px rgba(0, 0, 0, 0.5);
	transition: box-shadow 0.3s ease, transform 0.2s ease;
	text-align: left;
	cursor: pointer;
}

.project:hover {
	box-shadow: 0 5px 15px rgba(57, 73, 171, 0.9);
	transform: translateY(-2px);
}

.project h3 {
	margin-bottom: 0.3rem;
	color: #bbdefb;
	font-weight: 700;
	font-size: 1.1rem;
}

.project p {
	color: #b0bec5;
	margin-bottom: 0.6rem;
	font-size: 0.9rem;
	line-height: 1.3;
}

.project-link {
	color: #90caf9;
	font-weight: 600;
	font-size: 0.9rem;
	text-decoration: none;
	transition: color 0.3s ease;
}

.project-link:hover {
	color: #64b5f6;
	text-decoration: underline;
}

.contact {
	margin-top: 2rem;
	text-align: center;
	width: 100%;
}

.contact h2 {
	font-size: 1.6rem;
	color: #90caf9;
	margin-bottom: 0.8rem;
	font-weight: 600;
}

.contact p {
	font-size: 0.95rem;
	color: #cfd8dc;
}

.contact a {
	color: #64b5f6;
	text-decoration: none;
	font-weight: 600;
	font-size: 0.95rem;
}

.contact a:hover {
	text-decoration: underline;
}

@media (max-width: 600px) {
	.container {
		padding: 1rem 1.2rem;
		max-width: 100vw;
		height: 100vh;
		border-radius: 0;
	}

	.hero h1 {
		font-size: 1.8rem;
	}

	.hero p {
		font-size: 0.9rem;
		margin-bottom: 1rem;
	}

	.links a.btn {
		padding: 0.3rem 1rem;
		font-size: 0.75rem;
	}

	.projects h2 {
		font-size: 1.3rem;
	}

	.project {
		padding: 0.6rem 0.8rem;
	}

	.project h3 {
		font-size: 1rem;
	}

	.project p {
		font-size: 0.85rem;
	}
}
</style>
