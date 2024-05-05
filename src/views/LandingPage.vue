<template>
	<HeaderComponent />
	<AboutMeComponent />
	<ProjectsComponent />
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue';
import AboutMeComponent from '@/components/AboutMeComponent.vue';
import ProjectsComponent from '@/components/ProjectsComponent.vue';

export default {
	components: {
		HeaderComponent,
		AboutMeComponent,
		ProjectsComponent
	}
}
</script>
