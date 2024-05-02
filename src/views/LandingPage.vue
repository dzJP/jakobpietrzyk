<template>
	<div class="header-container">
		<div class="header-role">
			Java Full Stack Developer
		</div>
		<div class="header-name">
			Jakob Pietrzyk
		</div>
	</div>
	<div class="profile-picture">
		<img src="@/assets/jakob.jpg" alt="profile-picture">
	</div>
	<div class="welcome-text-container">
		<div class="welcome-text">
			Dedicated and highly motivated Java programmer with a strong background in Java programming, database
			development, and web development.
			Skilled in Java, JavaScript, and proficient in utilizing a diverse array of frameworks and tools.
			I thrive in environments that encourage creativity, collaboration, and continuous learning.
			With an eagerness to learn, I'm constantly looking for oppurtunities to deepen my existing knowledge as well
			as broaden my skill set.
		</div>
	</div>
	<div class="skills-section-container">
		<div class="skills-title">
			My skills
		</div>
		<div class="skills-section">
			Java & JavaScript | Spring Boot Framework | Spring Data/JPA | Spring MVC/REST | JWT | Mockito | JUnit | HTML
			| HTTP | CSS | Node.js | Vue.js | React | Git |
			Maven | Gradle | Docker | Azure | Figma | MySQL | Agile methodologies
		</div>
	</div>
	<div class="project-section-container">
		<div class="project-section-title">
			My projects
		</div>
		<div class="projects">
			<div class="project-image" :class="{ 'expanded': isImageExpanded }">
				<img :src="currentImage" alt="project-image" @click="toggleImageSize">
				<div class="navigation-buttons" v-if="isImageExpanded">
					<button @click="showLogin">Previous</button>
					<button @click="showForgotPassword">Next</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			loginImage: require('@/assets/login.png'),
			forgotPasswordImage: require('@/assets/forgotPassword.png'),
			currentImage: '',
			isImageExpanded: false,
		};
	},
	created() {
		this.currentImage = this.loginImage;
	},
	methods: {
		showLogin() {
			this.currentImage = this.loginImage;
		},
		showForgotPassword() {
			this.currentImage = this.forgotPasswordImage;
		},
		toggleImageSize() {
			this.isImageExpanded = !this.isImageExpanded;
		}
	},
};
</script>

<style>
.header-container {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	margin-top: 20vh;
	margin-left: 70vh;

}

.header-role {
	font-size: 25px;
	letter-spacing: 5px;
}

.header-name {
	font-size: 60px;
	text-transform: uppercase;
	letter-spacing: 10px;
	padding-bottom: 15px;

}

.profile-picture {
	position: absolute;
	top: 15%;
	left: 15%;
}

.profile-picture img {
	max-width: 200px;
	border: 2px solid var(--orange);
	border-radius: 50%;
	/* transform: scaleX(-1); */
}

.welcome-text-container {
	width: 100%;
	background-color: var(--dark-blue);
	border: 2px solid var(--blue);
}

.welcome-text {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	font-size: 20px;
	margin-left: auto;
	margin-right: auto;
	overflow-wrap: break-word;
	max-width: 80vh;
	padding: 10vh;
}

.skills-section-container {
	background-color: var(--dark-blue);
	border: 2px solid var(--blue);
	width: 100%;
	margin-top: 5px;
}

.skills-title {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	text-transform: uppercase;
	letter-spacing: 10px;
	padding-top: 10vh;
	font-size: 40px;
}

.skills-section {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	text-transform: uppercase;
	letter-spacing: 3px;
	margin-left: auto;
	margin-right: auto;
	margin-bottom: 5vh;
	font-size: 18px;
	max-width: 65vh;
	padding: 10px;
}

.project-section-title {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	text-transform: uppercase;
	letter-spacing: 10px;
	padding-top: 5vh;
	font-size: 40px;
}

.projects {
	display: flex;
	align-items: center;
	margin-bottom: 50vh;
}

.projects img {
	max-width: 400px;
	border: 1px solid var(--orange);
	border-radius: 5%;
	margin-left: 20vh;
	transition: transform 0.5s ease-in-out;
}

.project-image {
	transition: transform 0.5s;
}

.project-image.expanded {
	transform: scale(2);
}

.navigation-buttons {
	position: absolute;
	bottom: 15px;
	left: 55%;
	z-index: 1;
}
</style>
