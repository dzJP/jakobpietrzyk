<template>
    <section class="skills" id="skills">
        <h2 class="heading">
            <span>My skills</span>
        </h2>
        <div class="skills-container">
            <div class="skills-box">
                <div class="skills-icon1">
                    <h3>Backend Development</h3>
                    <p>I specialize in crafting robust, scalable applications with efficient code testing, ensuring
                        optimal data management, server logic, and performance, backed by secure authentication
                        measures.
                    </p>
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
                    <p>Specializing in creating functional and user-friendly interfaces, websites, and applications in
                        Java & JavaScript, ensuring seamless user experiences and efficient performance.</p>
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
    flex-wrap: wrap;
    flex-direction: row;
    justify-content: center;
    align-items: stretch;
    gap: 2rem;
}

.skills-container .skills-box {
    color: var(--white);
    flex: 1 1 30rem;
    background: var(--light-gray);
    padding: 2rem 0.2rem 3rem;
    border-radius: 2rem;
    text-align: center;
    border: .2rem solid var(--lightest-gray);
    transition: .5s ease;
    overflow: hidden;

}

.skills-box:hover {
    transform: scale(1.05);
    border-color: var(--blue-heaven);
}

.skills-box h3 {
    font-size: 1.4em;
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

@media (max-width: 360px) {
    .heading {
        text-align: center;
        font-size: 4.5rem;
    }

    .skills-box {
        padding: 0 !important;
    }

    span {
        font-size: 1em !important;
        letter-spacing: 10px;
        font-weight: 700;
        text-shadow: 1px 1px 2px color #ffffff;
    }

    .skills-box a.button {
        margin: 35px 15px;
        
    }

    .skills-box p {
        font-size: 1em;
        letter-spacing: 2px;
    }

}
</style>