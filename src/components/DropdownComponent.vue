<template>
    <div class="dropdown-container">
        <div class="dropdown" @click="toggleDropdown" @mouseleave="closeDropdown">
            <div class="dropdown-toggle">
                <span class="dropdown-icon">▼</span>
            </div>
            <ul class="dropdown-menu" :class="{ 'show': isDropdownOpen }">
                <li @click="handleItemClick('Home')">Home</li>
                <li @click="handleItemClick('About')">About</li>
                <li @click="handleItemClick('Contact')">Contact</li>
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
        toggleDropdown() {
            console.log('Toggle dropdown');
            this.isDropdownOpen = !this.isDropdownOpen;
        },
        closeDropdown() {
            console.log('Close dropdown');
            this.isDropdownOpen = false;
        },
        scrollToSection() {
            const projectsSection = document.getElementById('projects');
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
    top: 15px;
    right: 5%;
    cursor: pointer;
}

.dropdown-toggle {
    position: absolute;
    top: 0;
    right: 0;
    padding: 5px;
}

.dropdown-icon {
    font-size: 35px;
    color: var(--white);
    transition: color 0.5s ease-in;
    text-shadow: 1px 1px 10px #9ad7ff;
}

.dropdown-icon:hover {
    color: var(--blue-heaven);
    transition: color 0.3s ease-in-out;
}

.dropdown-menu {
    position: absolute;
    top: 20px;
    right: -55px;
    display: none;
    background-color: rgb(17, 17, 17);
    border: 1px solid #ccc;
    width: 150px;
    height: 220px;
    font-size: 22px;
    align-items: center;
    list-style-type: none;
    text-transform: uppercase;
    text-align: center;
    padding: 0;
    font-weight: 600;
}

.dropdown-menu li {
    margin: 5px;
    padding: 10px;
}

.dropdown-menu.show {
    display: block;
    color: var(--white);
}

.dropdown-menu.show li {
    transition: color 0.3s ease-in;
}

.dropdown-menu.show li:hover {
    color: var(--blue-heaven);
    cursor: pointer;
    transition: color 0.3s ease-in-out;
}
a,
a:visited {
    color: inherit; /* Keeps the same color as the normal link */
    text-decoration: none;
}
</style>