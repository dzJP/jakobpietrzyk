<template>
    <section class="skills" id="skills">
        <h2 class="heading">
            <span>My skills</span>
        </h2>
        <div class="skills-container">
            <div class="skills-box">
                <div class="skills-icon1">
                    <h3>Backend Development</h3>
                    <p>Genom att skapa backend i webbplatser och appar, hanterar backend-utveckling data,
                        serverlogik och säkerställer felfri funktionalitet</p>
                    <a href="#contact" class="button">Contact me</a>
                </div>
            </div>
            <div class="skills-box">
                <div class="skills-icon2">
                    <h3>Java & JavaScript</h3>
                    <p>Spring Boot Framework | Spring Data/JPA | Spring MVC/REST | JWT | Mockito | JUnit | HTML
                    | HTTP | CSS | Node.js | Vue.js | React | Git |
                    Maven | Gradle | Docker | Azure | Figma | MySQL | Agile methodologies</p>
                    <a href="#contact" class="button">Contact me</a>
                    </div>
            </div>
            <div class="skills-box">
                <div class="skills-icon3">
                    <h3>Web Development</h3>
                    <p>Skapar funktionella och användarvänliga webbplatser och applikationer i Java & JavaScript</p>
                    <a href="#contact" class="button">Contact me</a>
                </div>
            </div>
        </div>
    </section>
</template>

<style>

.heading {
    text-align: center;
    font-size: 4.5rem;
}

.skills {
    border-top: solid 1px var(--lightest-gray);
}
.skills-container {
    background-color: var(--dark-gray);
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 2rem;
    flex-wrap: wrap;
}

.skills-container .skills-box {
    color: var(--white);
    flex: 1 1 30rem;
    background: var(--light-gray);
    padding: 1rem 1rem 4rem;
    border-radius: 2rem;
    text-align: center;
    border: .2rem solid var(--lightest-gray);
    transition: .5s ease;
}

.skills-box:hover {
    transform: scale(1.05);
    border-color: var(--blue-heaven);
}

.skills-box h3 {
    font-size: 1.5em;
    letter-spacing: 3px;
}

.skills-box p {
    font-size: 1em;
    letter-spacing: 2px;
}

.skills-box h3,
.skills-box p {
    margin: 50px;
}

section {
    min-height: 100vh;
    padding: 2rem 10% 1rem;
}

</style>