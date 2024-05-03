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
			With an eagerness to learn, I'm constantly looking for opportunities to deepen my existing knowledge as well
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
			<div class="project-image" :class="{ 'expanded': isImageExpanded }" @click="toggleImageSize"
				@mouseleave="handleMouseLeave">
				<img :src="currentImage" alt="project-image">
				<div class="overlay-text" v-if="!isImageExpanded">
					Intranet development
				</div>

				<!-- Move navigation buttons inside the project-image div -->
				<div class="navigation-buttons" :class="{ 'visible': isImageExpanded }">
					<button class="button" @click="navigate('previous')">Previous</button>
					<button class="button" @click="navigate('next')">Next</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			images: [
				require('@/assets/login.png'),
				require('@/assets/forgotPassword.png'),
				require('@/assets/receivedPassword.png'),
				require('@/assets/homepageUser.png'),
				require('@/assets/adminpage.png'),
				require('@/assets/adminpageInviteUsers.png'),
				require('@/assets/receivedInvitation.png'),
				require('@/assets/signuppage.png'),
				require('@/assets/adminpageCreateNews.png'),
				require('@/assets/adminpageCreatedNews.png'),
				require('@/assets/adminpageLatestNews.png'),
				require('@/assets/adminpageOldestNews.png'),
				require('@/assets/adminpageSearchNews1.png'),
				require('@/assets/adminpageSearchNews2.png'),
				require('@/assets/adminpageEditNews.png'),
				require('@/assets/adminpageEditedNews.png'),
				require('@/assets/adminpageSelectedNews.png'),
				require('@/assets/adminpageNewsNavigate1.png'),
				require('@/assets/adminpageNewsNavigate2.png'),
				require('@/assets/receivedSharedNews.png'),
				require('@/assets/adminpageEditUser.png'),
				require('@/assets/adminpageEditUserPopup1.png'),
				require('@/assets/adminpageEditUserPopup2.png'),
				require('@/assets/adminpageEditedUser.png'),
				require('@/assets/adminpageCreateProject.png'),
				require('@/assets/adminpageEditProject.png'),
				require('@/assets/homepageAdminRegisterHours.png'),
				require('@/assets/profilePage.png'),
				require('@/assets/colleaguesPage.png')
			],
			currentImageIndex: 0,
			isImageExpanded: false,
		};
	},
	computed: {
		currentImage() {
			return this.images[this.currentImageIndex];
		}
	},
	methods: {
		navigate(direction) {
			if (direction === 'previous') {
				this.currentImageIndex = (this.currentImageIndex - 1 + this.images.length) % this.images.length;
			} else if (direction === 'next') {
				this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
			}
		},
		toggleImageSize(event) {
			// Check if the click event originates from the image itself
			if (event.target.tagName.toLowerCase() === 'img') {
				// Toggle the state of isImageExpanded
				this.isImageExpanded = !this.isImageExpanded;
				const overlayText = document.querySelector('.overlay-text');
				if (overlayText) {
					overlayText.style.display = this.isImageExpanded ? 'none' : 'block';
				}
			}
		},
		handleMouseLeave(event) {
			const expandedImage = document.querySelector('.project-image.expanded');
			if (expandedImage && !expandedImage.contains(event.relatedTarget)) {
				this.isImageExpanded = false;
			}
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
	margin-top: 20px;
	margin-bottom: 20%;
}

.projects img {
	max-width: 400px;
	border: 1px solid var(--orange);
	border-radius: 5%;
	margin-left: 20vh;
	transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
	opacity: 0.2;
}

.projects img:hover {
	opacity: 1;
}

.project-image {
	position: relative;
	display: flex;
	justify-content: center;
	align-items: center;
	transition: transform 0.5s;
	cursor: pointer;
}

.project-image.expanded {
	transform: scale(3);
	margin-left: 5%;
}

.project-image.expanded img {
	opacity: 1;
}

.overlay-text {
	position: absolute;
	top: 42%;
	left: 42%;
	color: white;
	font-size: 20px;
	text-transform: uppercase;
	letter-spacing: 2px;
	opacity: 1;
	transition: opacity 0.5s ease-in-out;
	pointer-events: none;
}

.project-image.expanded .overlay-text {
	display: none;
}

.project-image:hover .overlay-text {
	opacity: 0;
}

.navigation-buttons {
	position: absolute;
	bottom: 10px;
	left: 50%;
	transform: translateX(-50%);
	z-index: 1;
	opacity: 0;
	transition: opacity 0.8s ease-in-out;
}

.project-image.expanded .navigation-buttons {
	opacity: 1;
}

.navigation-buttons .button {
	font-size: 16px;
	font-family: 'Oxanium', sans-serif;
	color: var(--white);
	background-color: var(--light-blue);
	border: none;
	border-radius: 5px;
	padding: 8px 20px;
	margin-right: 10px;
	cursor: pointer;
	transition: background-color 0.3s ease;
}

.navigation-buttons .button:hover {
	background-color: var(--light-blue-hover);
}
</style>