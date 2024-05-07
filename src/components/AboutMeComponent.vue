<template>
    <div class="about-me-section-container">
        <div class="about-me-section">
            Dedicated and highly motivated Java programmer with a strong background in Java programming, database
            development, and web development.
            Skilled in Java, JavaScript, and proficient in utilizing a diverse array of frameworks and tools.
            I thrive in environments that encourage creativity, collaboration, and continuous learning.
            With an eagerness to learn, I'm constantly looking for opportunities to deepen my existing knowledge as well
            as broaden my skill set.
        </div>
    </div>
    <div id="about" class="my-skills-container">
		<div class="my-skills-title">
			My skills
		</div>
		<div class="my-skills-text">
			Java & JavaScript | Spring Boot Framework | Spring Data/JPA | Spring MVC/REST | JWT | Mockito | JUnit | HTML
			| HTTP | CSS | Node.js | Vue.js | React | Git |
			Maven | Gradle | Docker | Azure | Figma | MySQL | Agile methodologies
		</div>
	</div>
</template>

<style>
.about-me-section-container {
	width: 100%;
	background-color: var(--darker-gray-black);
	border-bottom: solid 2px var(--dark-gray-black)

}

.about-me-section {
	position: relative;
	flex-direction: column;
	align-items: center;
	text-align: center;
	margin-left: auto;
    margin-right: auto;
	font-size: 16px;
	letter-spacing: 2px;
	width: 50%;
	padding: 5%;
}

.my-skills-container {
	width: 100%;
	background-color: var(--darker-gray-black);
	padding-bottom: 5%;
}

.my-skills-title {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	text-transform: uppercase;
	letter-spacing: 10px;
	padding-top: 5%;
	margin-bottom: 15px;
	font-size: 40px;
}

.my-skills-text {
	color: #ffffff94;
	margin-left: auto;
	margin-right: auto;
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	text-transform: uppercase;
	letter-spacing: 3px;
	font-size: 18px;
	max-width: 30%;
	padding-bottom: 50px;
}

</style>