<template>
    <div class="dropdown-container">
        <div class="dropdown" @mouseover="openDropdown" @mouseleave="closeDropdown">
            <div class="dropdown-toggle">
                <span class="dropdown-icon" :class="{ 'open': isDropdownOpen }">➤</span>
            </div>
            <ul class="dropdown-menu" :class="{ 'show': isDropdownOpen }">
                <li><a href="#home" @click="scrollToSection">Home</a></li>
                <li><a href="#about" @click="scrollToSection">About</a></li>
                <li><a href="#contact" @click="scrollToSection">Contact</a></li>
                <li><a href="#projects" @click="scrollToSection">Projects</a></li>
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
    top: 0px;
    right: 10%;
    cursor: default; /* Change cursor to default when list is hidden */
}

.dropdown-menu {
    position: absolute;
    top: 35px;
    left: -75px;
    width: 200px;
    opacity: 0;
    padding: 0;
    align-items: center;
    text-align: center;
    list-style-type: none;
    text-transform: uppercase;
    pointer-events: none;
    overflow:hidden;
    font-weight: 600;
    font-size: 22px;
    transition: opacity 0.3s ease;
    border: 2px solid var(--lightest-gray);
    background-color: rgb(17, 17, 17);

}

.dropdown-menu.show {
    opacity: 1;
    color: var(--white);
    height: auto;
    pointer-events: auto; /* Enable pointer events when list is shown */
}

.dropdown-menu.show li {
    transition: color 0.3s ease-in;
}

.dropdown-menu.show li:hover {
    color: var(--blue-heaven);
    transition: color 0.3s ease-in-out;
}

.dropdown-icon {
    font-size: 3em;
    color: var(--white);
    transition: color 0.5s ease-in;
    text-shadow: 1px 1px 10px #9ad7ff;
    display: inline-block;
    transform: rotate(90deg);
}

.dropdown-icon:hover {
    color: var(--blue-heaven);
    transition: color 0.3s ease-in-out;
}

a,
a:visited {
    color: inherit; /* Keeps the same color as the normal link */
    text-decoration: none;
}

@media (max-width: 1366px) {
    .dropdown-menu {
        left: -5em;
    }
}
</style>
