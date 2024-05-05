<template>
	<HeaderComponent />
	<div class="welcome-text-container">
		<div class="welcome-text">
			Dedicated and highly motivated Java programmer with a strong background in Java programming, database
			development, and web development.
			Skilled in Java, JavaScript, and proficient in utilizing a diverse array of frameworks and tools.
			<br>I thrive in environments that encourage creativity, collaboration, and continuous learning.
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
			<div class="project-image" :class="{ 'expanded': isImageExpanded }" @mouseleave="handleMouseLeave">
				<img :src="currentImage" alt="project-image">
				<div class="overlay-text" v-if="!isImageExpanded">
					Intranet development
				</div>
				<div class="navigation-buttons" :class="{ 'visible': isImageExpanded }">
					<button class="button" @click="navigate('previous')">Previous</button>
					<button class="button" @click="navigate('next')">Next</button>
				</div>
			</div>
			<div class="project-description-deltma" v-if="!isImageExpanded">
				A secure and efficient internal network for streamlined communication, collaboration, and information
				sharing.
			</div>
			<div class="link-to-repo-intranet">
				<a href="https://github.com/dzJP/intranet">Repository</a>
			</div>
			<div class="project-video">
				<video controls>
					<source src="@/assets/worldwidepancakes.mp4" type="video/mp4">
					Your browser does not support the video tag.
				</video>
				<div class="overlay-text" v-if="!isImageExpanded">
					World Wide Pancakes
				</div>
				<div class="project-description-worldwidepancakes" v-if="!isImageExpanded">
					World Wide Pancakes is a web app where pancake enthusiasts can discover, share, and connect over
					delicious recipes.
				</div>
				<div class="link-to-repo-worldwidepancakes">
				<a href="https://github.com/dzJP/worldwidepancakes">Repository</a>
			</div>
			</div>
		</div>
	</div>
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue';
export default {
	components: {
		HeaderComponent
	},
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
	font-size: 16px;
	letter-spacing: 2px;
	margin-left: auto;
	margin-right: auto;
	word-wrap: break-word;
	width: 40%;
	padding: 5%;
}

.skills-section-container {
	background-color: var(--dark-blue);
	border-bottom: 2px solid var(--blue);
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
	padding-top: 40px;
	margin-bottom: 30px;
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
	margin-bottom: 40px;
	font-size: 18px;
	max-width: 30%;
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
	margin-top: 40px;
	font-size: 40px;
}


.projects {
	display: flex;
	align-items: center;
	margin-left: 10%;
	margin-top: 5%;
	margin-bottom: 20%;
}

.project-image img {
	max-width: 400px;
	border: 1px solid #333333;
	border-radius: 5%;
	transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
	opacity: 0.4;
}

.project-image:hover img {
	opacity: 1;
}

.project-image {
	position: relative;
	display: flex;
	left: 5%;
	transition: transform 1s;
}

.project-image:hover {
	transform: scale(2);
	z-index: 3;
}

.project-image:hover .navigation-buttons {
	opacity: 1;
}

.overlay-text {
	position: absolute;
	top: 42%;
	left: 15%;
	color: white;
	font-size: 20px;
	text-transform: uppercase;
	letter-spacing: 2px;
	opacity: 1;
	pointer-events: none;
	white-space: nowrap;
	transition: transform 0.8s ease-in-out, opacity 0.8s ease-in-out;
}

.project-image:hover .overlay-text {
	opacity: 0;
}

.project-image img:hover {
	opacity: 1 !important;
}

.navigation-buttons {
	position: absolute;
	bottom: 10px;
	left: 50%;
	transform: translateX(-50%);
	z-index: 1;
	opacity: 0;
	transition: opacity 1s ease-in-out;
}

.project-image.expanded .navigation-buttons {
	opacity: 1;
}

.navigation-buttons .button {
	color: var(--white);
	background-color: var(--light-blue);
	font-size: 16px;
	font-family: 'Oxanium', sans-serif;
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

.project-description-deltma {
	position: absolute;
	margin-top: 16%;
	left: 25%;
	transform: translateX(-50%);
	letter-spacing: 2px;
	text-align: center;
	font-size: 16px;
	color: white;
	width: 20%;
	z-index: -1;
	pointer-events: none;
}
.link-to-repo-worldwidepancakes {
	left: 42% !important;
}
a:visited {
	color: var(--orange);
}

.link-to-repo-intranet a,
.link-to-repo-worldwidepancakes {
	position: absolute;
	bottom: -55%;
	left: 24%;
	transform: translate(-50%, -50%); /* center with top left and transform */
	text-align: center;
	text-shadow: 2px 2px 4px var(--dark-blue);
	z-index: 3;
	color: var(--orange);
	font-size: 18px;
	font-weight: 600;
	text-transform: uppercase;
	text-decoration: none;
	letter-spacing: 2px;
	
}

.project-video {
	position: absolute;
	align-items: center;
	left: 65%;
	right: 10%;
}

.project-video video {
	max-width: 400px;
	margin-top: 15px;
	opacity: 0.1;
	border: 1px solid #333333;
	border-radius: 1%;
	outline: none;
	cursor: pointer;
	transition: transform 0.8s ease-in-out, opacity 0.8s ease-in-out;
}

.project-video video:hover {
	opacity: 1;
	transform: scale(1.75);

}

.project-video:hover .overlay-text {
	transform: scale(1.5);
	opacity: 0;
}

.project-description-worldwidepancakes {
	position: absolute;
	text-align: center;
	margin-top: 15px;
	left: 42%;
	font-size: 14px;
	color: white;
	transform: translateX(-50%);
	width: 100%;
	z-index: -1;
	pointer-events: none;
	letter-spacing: 2px;
}
</style>