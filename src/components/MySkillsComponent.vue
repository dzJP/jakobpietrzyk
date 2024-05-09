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
    padding: 1rem 2rem 4rem;
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

@media (max-width: 1366px) {
    section {
        padding: 2rem 10% 6rem !important;
    }

    .skills-box {
        padding: 5px 1% 2rem !important;
    }

    .heading {

        margin-bottom: 15%;
    }

    span {
        font-size: 0.5em !important;
        letter-spacing: 10px;
        font-weight: 700;
        text-shadow: 1px 1px 2px color #ffffff;
    }

    .skills-box h3,
    .skills-box p {
        margin: 25px;
        
    }
    .skills-box p {
        font-size: 0.9em;
    }

    .button {
        font-size: 1em;
        letter-spacing: 5px !important;
    }

}
@media (max-width: 768px) {
    section {
        padding: 2rem 10% 6rem !important;
    }

    .skills-box {
        padding: 5px 1% 2rem !important;
    }

    .heading {

        margin-bottom: 15%;
    }

    span {
        font-size: 0.5em !important;
        letter-spacing: 10px;
        font-weight: 700;
        text-shadow: 1px 1px 2px color #ffffff;
    }

    .skills-box h3,
    .skills-box p {
        margin: 25px;
        
    }
    .skills-box p {
        font-size: 0.9em;
    }

    .button {
        font-size: 1em;
        letter-spacing: 5px !important;
    }

}
</style>