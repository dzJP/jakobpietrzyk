<template>
	<HeadComponent />
	<HeaderComponent />
	<AboutMeComponent />
	<ProjectsComponent />
</template>

<script>
import HeadComponent from '@/components/HeadComponent.vue';
import HeaderComponent from '@/components/HeaderComponent.vue';
import AboutMeComponent from '@/components/AboutMeComponent.vue';
import ProjectsComponent from '@/components/ProjectsComponent.vue';

export default {
	components: {
		HeadComponent,
		HeaderComponent,
		AboutMeComponent,
		ProjectsComponent
	}
}
</script>
