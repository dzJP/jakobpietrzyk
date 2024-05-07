<template>
	<div id="home">
	<HeadComponent />
	<HeaderComponent />
	<AboutMeComponent />
	<ProjectsComponent />
	<ContactMeComponent />
</div>
</template>

<script>
import HeadComponent from '@/components/HeadComponent.vue';
import HeaderComponent from '@/components/HeaderComponent.vue';
import AboutMeComponent from '@/components/AboutMeComponent.vue';
import ProjectsComponent from '@/components/ProjectsComponent.vue';
import ContactMeComponent from '@/components/ContactMeComponent.vue';

export default {
	components: {
		HeadComponent,
		HeaderComponent,
		AboutMeComponent,
		ProjectsComponent,
		ContactMeComponent,
	}
}
</script>
