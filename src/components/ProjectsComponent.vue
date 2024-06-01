<template>
    <div id="projects" class="project-section-container">
        <div class="project-section-title">My projects</div>
        <div class="projects">
            <IntranetProject />
            <WorldWidePancakesProject />
            <WebShopProject />
        </div>
    </div>
</template>
<script>
import IntranetProject from '@/components/IntranetProject.vue';
import WorldWidePancakesProject from '@/components/WorldWidePancakesProject.vue';
import WebShopProject from '@/components/WebShopProject.vue';

export default {
    components: {
        IntranetProject,
        WorldWidePancakesProject,
        WebShopProject,
    }
}

</script>
<style>
.project-section-container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 4rem;
    background-color: var(--gray-black);
    border-top: solid 1px var(--lightest-gray);
}

.project-section-title {
    display: flex;
    flex-direction: row;
    justify-content: center;
    font-size: 2.6em;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 10px;
    margin-top: 5%;
    font-size: 40px;
}

.projects {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: flex-end;
    gap: 4rem;
    padding: 20px;
    width: 75%;
    padding: 5%;
    margin-bottom: 15%;
}

.project {
    position: relative;
    z-index: 1;
    margin-bottom: 15%;
}

.project-image img,
.project-video video {
    width: 400px;
    border: 2px solid var(--orange);
    border-radius: 5%;
    transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
    opacity: 0.4;
}

.project-image img {
    margin-bottom: 15px !important;
}

.project-image:hover img,
.project-video:hover video {
    opacity: 1;
    transform: scale(1.75);
}

.navigation-buttons {
    display: flex;
    position: absolute;
    bottom: 10px;
    left: 50%;
    height: 5px;
    transform: translateX(-50%);
    z-index: 1;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
}

.project-image:hover .navigation-buttons {
    opacity: 1;
}

.navigation-buttons button {
    color: var(--white);
    background-color: var(--orange);
    font-size: 26px;
    text-align: center;
    border: none;
    border-radius: 5px;
    height: 40px;
    padding: 4px 20px;
    margin-right: 10px;
    cursor: pointer;
    transition: background-color 0.5s ease;
    box-shadow: 0 0 1rem var(--orange);
}

.navigation-buttons button:hover {
    background-color: var(--orange-hover);
}

.project-image:hover .overlay-text,
.project-video:hover .overlay-text {
    opacity: 0;
    transform: scale(1.5);
}

.overlay-text {
    position: absolute;
    top: 40%;
    left: 8%;
    color: rgba(255, 255, 255, 0.642);
    font-size: 25px;
    font-weight: 400;
    text-transform: uppercase;
    letter-spacing: 2px;
    opacity: 1;
    pointer-events: none;
    white-space: nowrap;
    transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
}

.project-image:hover .overlay-text {
    opacity: 0;
}

.project-description {
    position: absolute;
    bottom: -40%;
    left: 10%;
    width: 75%;
    margin-left: 15px;
    letter-spacing: 2px;
    text-align: center;
    font-size: 16px;
    color: white;
    z-index: -2;
    pointer-events: none;
}

.link-to-repo a {
    position: absolute;
    bottom: -65%;
    left: 50%;
    transform: translate(-50%, -50%);
    height: auto;
    padding: 5px 15px;
    font-size: 16px;
    letter-spacing: 2px;
    color: var(--orange);
    text-align: center;
    text-transform: uppercase;
    text-decoration: none;
    text-shadow: 2px 2px 4px var(--dark-blue);
    z-index: 2;
}

a.visited,
a.link {
    color: var(--orange);
    text-decoration: none;
}

@media (max-width: 1366px) {

    .projects {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        width: 75%;
        padding: 5%;
        margin-bottom: 35%;
    }

    .project {
        margin-bottom: 60%;
    }

    .navigation-buttons button {
        color: var(--white);
        background-color: var(--orange);
        font-size: 26px;
        font-family: 'Oxanium', sans-serif;
        text-align: center;
        border: none;
        border-radius: 5px;
        height: 40px;
        padding: 4px 20px;
        margin-right: 10px;
        cursor: pointer;
        transition: background-color 0.5s ease;

    }

    .project-image:hover img,
    .project-video:hover video {
        opacity: 1;
        transform: scale(1.5);
    }

}

@media (max-width: 768px) {

    .projects {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        width: 75%;
        padding: 5%;
        margin-bottom: 35%;
    }

    .project {
        margin-bottom: 60%;
    }

    .navigation-buttons button {
        color: var(--white);
        background-color: var(--orange);
        font-size: 26px;
        font-family: 'Oxanium', sans-serif;
        text-align: center;
        border: none;
        border-radius: 5px;
        height: 40px;
        padding: 4px 20px;
        margin-right: 10px;
        cursor: pointer;
        transition: background-color 0.5s ease;

    }

    .project-image:hover img,
    .project-video:hover video {
        opacity: 1;
        transform: scale(1.5);
    }

}

@media (max-width: 360px) {
    .projects {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        min-width: 100vh;
        padding: 1em;
        margin-bottom: 35%;
    }

    .project-section-title {
        display: flex;
        flex-direction: row;
        justify-content: center;
        text-wrap: nowrap;
        text-transform: uppercase;
        font-weight: 700;
        font-size: 2em;
        letter-spacing: 5px;
        margin: 30% 0;
    }

    .project-image:hover img,
    .project-video:hover video {
        opacity: 1;
        transform: scale(1.35);
    }

    .project-image img,
    .project-video video {
        width: 265px;
        height: auto;
        border: 2px solid var(--orange);
        border-radius: 5%;
        transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
        opacity: 0.4;
    }

    .overlay-text {
        position: absolute;
        top: 40%;
        left: 6%;
        color: var(--white);
        font-size: 1em;
        font-weight: 400;
        text-transform: uppercase;
        letter-spacing: 2px;
        opacity: 1;
        pointer-events: none;
        white-space: nowrap;
        transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
    }

    .navigation-buttons button {
        background-color: var(--orange);
        font-size: 1.5em;
        text-align: center;
        border: none;
        border-radius: 5px;
        height: 40px;
        padding: 4px 20px;
        margin-right: 10px;
        cursor: pointer;
        transition: background-color 0.5s ease;
        box-shadow: 0 0 1rem var(--orange);
    }

    .navigation-buttons button:hover {
        background-color: var(--orange-hover);
    }

    .project-description {
        position: absolute;
        top: 11.5em;
        left: -5%;
        width: 100%;
        margin-left: 15px;
        letter-spacing: 2px;
        font-size: 1em;
        text-align: center;
        color: white;
        z-index: -2;
        pointer-events: none;
    }

    .link-to-repo a {
        position: absolute;
        top: 20em;
        left: 50%;
        transform: translate(-50%, -50%);
        height: auto;
        padding: 5px 15px;
        font-size: 16px;
        letter-spacing: 2px;
        color: var(--orange);
        text-align: center;
        text-transform: uppercase;
        text-decoration: none;
        text-shadow: 2px 2px 4px var(--dark-blue);
        z-index: 2;
    }

    a.visited,
    a.link {
        color: var(--orange);
        text-decoration: none;
    }

}

@media (max-width: 414px) {

    .projects {
        display: flex;
        width: 100%;
    }

    .project-section-title {
        margin-top: 3em;
        font-size: 2em;
    }

    .project-description {
        position: absolute;
        left: -10px;
        top: 9em;
        width: 100%;
        margin: 10px 10px;
        letter-spacing: 2px;
        text-align: center;
        color: white;
        z-index: -2;
        pointer-events: none;
        font-size: 1.2em !important;
    }

    .link-to-repo a {
        position: absolute;
        top: 10em;
        left: 50%;
        height: auto;
        margin-top: 25px;
        font-size: 2em;
        letter-spacing: 2px;
        color: var(--orange);
        text-align: center;
        text-transform: uppercase;
        text-decoration: none;
        text-shadow: 2px 2px 4px var(--dark-blue);
        z-index: 2;
    }

}
</style>