<template>
	<div id="home">
		<HeadComponent />
    </div>
		<HeaderComponent />
		<AboutMeComponent />
		<MySkillsComponent />
		<ProjectsComponent />
		<ContactMeComponent />

</template>

<script>
import HeadComponent from '@/components/HeadComponent.vue';
import HeaderComponent from '@/components/HeaderComponent.vue';
import AboutMeComponent from '@/components/AboutMeComponent.vue';
import MySkillsComponent from '@/components/MySkillsComponent.vue';
import ProjectsComponent from '@/components/ProjectsComponent.vue';
import ContactMeComponent from '@/components/ContactMeComponent.vue';

export default {
	components: {
		HeadComponent,
		HeaderComponent,
		AboutMeComponent,
		MySkillsComponent,
		ProjectsComponent,
		ContactMeComponent,
	},
	mounted() {
        const fragment = window.location.hash;
        if (fragment) {
            const targetId = fragment.substring(1);
            const targetSection = document.getElementById(targetId);
            if (targetSection) {
                targetSection.scrollIntoView({ behavior: 'smooth' });
            }
        } else {
            const defaultSection = document.getElementById('about');
            if (defaultSection) {
                defaultSection.scrollIntoView({ behavior: 'smooth' });
            }
        }
    }
};

</script>
