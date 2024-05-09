<template>
    <div class="dropdown-container">
        <div class="dropdown" @mouseover="openDropdown" @mouseleave="closeDropdown">
            <div class="dropdown-toggle">
                <span class="dropdown-icon" :class="{ 'open': isDropdownOpen }">›</span>
            </div>
            <ul class="dropdown-menu" :class="{ 'show': isDropdownOpen }">
                <li><a href="#home" @click="scrollToSection">Home</a></li>
                <li><a href="#about" @click="scrollToSection">About</a></li>
                <li><a href="#projects" @click="scrollToSection">Projects</a></li>
                <li><a href="#contact" @click="scrollToSection">Contact</a></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isDropdownOpen: false
        };
    },
    methods: {
        openDropdown() {
            this.isDropdownOpen = true;
        },
        closeDropdown() {
            this.isDropdownOpen = false;
        },
        scrollToSection() {
            const projectsSection = document.getElementById('projects', 'contact', 'home', 'about');
            if (projectsSection) {
                projectsSection.scrollIntoView({ behavior: 'smooth' });
            }
            this.isDropdownOpen = false;
        }
    }
};
</script>

<style scoped>
.dropdown-container {
    position: relative;
}

.dropdown {
    position: absolute;
    cursor: default;
    /* Change cursor to default when list is hidden */
}

.dropdown-menu {
    position: absolute;
    top: -0.5rem;
    left: 0.5rem;
    width: 200px;
    opacity: 0;
    padding: 0;
    font-weight: 700;
    font-size: 1rem;
    border: 2px solid var(--lightest-gray);
    background-color: rgb(17, 17, 17);
    list-style-type: none;
    pointer-events: none;
    overflow: hidden;
    transition: opacity 0.3s ease;
}

.dropdown-menu.show {
    opacity: 1;
    color: var(--white);
    height: auto;
    pointer-events: auto;
    /* Enable pointer events when list is shown */
}

.dropdown-menu li {
    padding: 10px 0;
    margin-bottom: 0;
}


.dropdown-menu.show li:hover {
    color: var(--blue-heaven);
    transition: color 0.3s ease-in-out;
}

.dropdown-icon {
    position: absolute;
    top: -5rem;
    left: 5rem;
    display: inline-block;
    font-size: 6em;
    text-shadow: 1px 1px 5px #9ad7ff;
    transform: rotate(90deg);
    transition: color 0.5s ease-in;
}

/* .dropdown-icon:hover {
    color: var(--blue-heaven);
    transition: color 0.3s ease-in-out;
} */

.dropdown-icon.open {
    color: var(--blue-heaven);
    transition: color 0.5s ease-in-out;
}

.dropdown-menu a,
.dropdown-menu a:visited {
    color: var(--white);
    display: flex;
    flex-direction: row;
    justify-content: center;
    font-size: 2em;
    letter-spacing: 5px;
    font-weight: 400;
    transition: color 0.3s ease-in;
}

.dropdown-menu a:hover {
    color: var(--blue-heaven);
    transition: color 0.3s ease-in-out;
}

a,
a:visited {
    color: inherit;
    /* Keeps the same color as the normal link */
    text-decoration: none;
}

@media (max-width: 1366px) {

    .dropdown-menu {
        position: absolute;
        width: 200px;
        opacity: 0;
        padding: 0;
        font-weight: 700;
        font-size: 1rem;
        border: 2px solid var(--lightest-gray);
        background-color: rgb(17, 17, 17);
        list-style-type: none;
        pointer-events: none;
        overflow: hidden;
        transition: opacity 0.3s ease;
    }
    .dropdown-icon {
        /* Adjust styles for screens up to 1366px wide */
        position: absolute;
        bottom: -45px;
        left: 70px;
        display: inline-block;
        font-size: 5em !important;
        text-shadow: 1px 1px 5px #9ad7ff;
        transform: rotate(90deg);
        transition: color 0.5s ease-in;
    }

}

@media (max-width: 768px) {
    .dropdown-icon {
        /* Adjust styles for screens up to 1366px wide */
        position: absolute;
        top: -5.25rem;
        left: 10rem;
        display: inline-block;
        font-size: 5em !important;
        text-shadow: 1px 1px 5px #9ad7ff;
        transform: rotate(90deg);
        transition: color 0.5s ease-in;
    }
    .dropdown-menu {
        position: absolute;
        top: 0rem;
        left: 6rem;
        width: 200px;
        opacity: 0;
        padding: 0;
        font-weight: 700;
        font-size: 1rem;
        border: 2px solid var(--lightest-gray);
        background-color: rgb(17, 17, 17);
        list-style-type: none;
        pointer-events: none;
        overflow: hidden;
        transition: opacity 0.3s ease;
    }
}
@media (max-width: 320px) {
    .dropdown-icon {
        position: absolute;
        top: -4.5rem;
        left: 1rem;
        display: inline-block;
        font-size: 5em !important;
        text-shadow: 1px 1px 5px #9ad7ff;
        transform: rotate(90deg);
        transition: color 0.5s ease-in;
    
    }
    .dropdown-menu {
        position: absolute;
        top: 0;
        left: 1rem;
        width: 200px;
        opacity: 0;
        padding: 0;
        font-weight: 700;
        font-size: 1rem;
        border: 2px solid var(--lightest-gray);
        background-color: rgb(17, 17, 17);
        list-style-type: none;
        pointer-events: none;
        overflow: hidden;
        transition: opacity 0.3s ease;
    }
}
</style>