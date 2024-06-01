<template>
    <div class="project">
        <div class="project-video">
            <video controls>
                <source src="@/assets/worldwidepancakes.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
            <div class="overlay-text" v-if="!isImageExpanded">World Wide Pancakes</div>
            <div class="project-description" v-if="!isImageExpanded">
                World Wide Pancakes is a web app where pancake enthusiasts can discover, share, and connect over
                delicious recipes.
            </div>
        </div>
        <div class="link-to-repo">
            <a href="https://github.com/dzJP/worldwidepancakes">Repository</a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isImageExpanded: false,
        };
    }
};
</script>

<style scoped>
</style>