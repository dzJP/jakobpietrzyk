<template>
    <div class="project-section-container">
        <div class="project-section-title">
            My projects
        </div>
        <div class="projects">
            <div class="project-image" :class="{ 'expanded': isImageExpanded }" @mouseleave="handleMouseLeave">
                <img :src="currentImage" alt="project-image">
                <div class="overlay-text" v-if="!isImageExpanded">
                    Intranet development
                </div>
                <div class="navigation-buttons" :class="{ 'visible': isImageExpanded }">
                    <button class="button" @click="navigate('previous')">Previous</button>
                    <button class="button" @click="navigate('next')">Next</button>
                </div>
            </div>
            <div class="project-description-deltma" v-if="!isImageExpanded">
                A secure and efficient internal network for streamlined communication, collaboration, and information
                sharing.
            </div>
            <div class="link-to-repo-intranet">
                <a href="https://github.com/dzJP/intranet">Repository</a>
            </div>
            <div class="project-video">
                <video controls>
                    <source src="@/assets/worldwidepancakes.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
                <div class="overlay-text" v-if="!isImageExpanded">
                    World Wide Pancakes
                </div>
                <div class="project-description-worldwidepancakes" v-if="!isImageExpanded">
                    World Wide Pancakes is a web app where pancake enthusiasts can discover, share, and connect over
                    delicious recipes.
                </div>
                <div class="link-to-repo-worldwidepancakes">
                    <a href="https://github.com/dzJP/worldwidepancakes">Repository</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            images: [
                require('@/assets/login.png'),
                require('@/assets/forgotPassword.png'),
                require('@/assets/receivedPassword.png'),
                require('@/assets/homepageUser.png'),
                require('@/assets/adminpage.png'),
                require('@/assets/adminpageInviteUsers.png'),
                require('@/assets/receivedInvitation.png'),
                require('@/assets/signuppage.png'),
                require('@/assets/adminpageCreateNews.png'),
                require('@/assets/adminpageCreatedNews.png'),
                require('@/assets/adminpageLatestNews.png'),
                require('@/assets/adminpageOldestNews.png'),
                require('@/assets/adminpageSearchNews1.png'),
                require('@/assets/adminpageSearchNews2.png'),
                require('@/assets/adminpageEditNews.png'),
                require('@/assets/adminpageEditedNews.png'),
                require('@/assets/adminpageSelectedNews.png'),
                require('@/assets/adminpageNewsNavigate1.png'),
                require('@/assets/adminpageNewsNavigate2.png'),
                require('@/assets/receivedSharedNews.png'),
                require('@/assets/adminpageEditUser.png'),
                require('@/assets/adminpageEditUserPopup1.png'),
                require('@/assets/adminpageEditUserPopup2.png'),
                require('@/assets/adminpageEditedUser.png'),
                require('@/assets/adminpageCreateProject.png'),
                require('@/assets/adminpageEditProject.png'),
                require('@/assets/homepageAdminRegisterHours.png'),
                require('@/assets/profilePage.png'),
                require('@/assets/colleaguesPage.png')
            ],
            currentImageIndex: 0,
            isImageExpanded: false,
        }
    },
    computed: {
        currentImage() {
            return this.images[this.currentImageIndex];
        },
        methods: {
            navigate(direction) {
                if (direction === 'previous') {
                    this.currentImageIndex = (this.currentImageIndex - 1 + this.images.length) % this.images.length;
                } else if (direction === 'next') {
                    this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
                }
            },
            toggleImageSize(event) {
                // Check if the click event originates from the image itself
                if (event.target.tagName.toLowerCase() === 'img') {
                    // Toggle the state of isImageExpanded
                    this.isImageExpanded = !this.isImageExpanded;
                    const overlayText = document.querySelector('.overlay-text');
                    if (overlayText) {
                        overlayText.style.display = this.isImageExpanded ? 'none' : 'block';
                    }
                }
            },
            handleMouseLeave(event) {
                const expandedImage = document.querySelector('.project-image.expanded');
                if (expandedImage && !expandedImage.contains(event.relatedTarget)) {
                    this.isImageExpanded = false;
                }
            }
        },
    },
}
</script>
<style>
.project-section-container {
    height: auto;
    width: auto;

}

.project-section-title {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    text-transform: uppercase;
    letter-spacing: 10px;
    margin-top: 40px;
    font-size: 40px;
}

.projects {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    align-items: flex-start;
    padding: 20px;
}

.project-image img {
    max-width: 400px;
    border: 1px solid #333333;
    border-radius: 5%;
    transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
    opacity: 0.4;

}

.project-image:hover img {
    opacity: 1;
}

.project-image {
    position: absolute;
    bottom: -30%;
    left: 11%;
    transition: transform 1s;
}

.project-image:hover {
    transform: scale(2);
    z-index: 3;
}

.project-image:hover .navigation-buttons {
    opacity: 1;
}

.overlay-text {
    position: absolute;
    top: 45%;
    left: 8%;
    color: rgba(255, 255, 255, 0.642);
    font-size: 25px;
    font-weight: 400;
    text-transform: uppercase;
    letter-spacing: 2px;
    opacity: 1;
    pointer-events: none;
    white-space: nowrap;
    transition: transform 0.8s ease-in-out, opacity 0.8s ease-in-out;
}

.project-image:hover .overlay-text {
    opacity: 0;
}

.project-image img:hover {
    opacity: 1 !important;
}

.navigation-buttons {
    position: absolute;
    bottom: 10px;
    left: 50%;
    height: 5px;
    transform: translateX(-50%);
    z-index: 1;
    opacity: 0;
    transition: opacity 1s ease-in-out;
}

.project-image.expanded .navigation-buttons {
    opacity: 1;
}

.navigation-buttons .button {
    color: var(--white);
    background-color: var(--light-blue);
    font-size: 16px;
    font-family: 'Oxanium', sans-serif;
    text-align: center;
    border: none;
    border-radius: 5px;
    height: 30px;
    padding: 4px 20px;
    margin-right: 10px;
    cursor: pointer;
    transition: background-color 0.5s ease;
}

.navigation-buttons .button:hover {
    background-color: var(--light-blue-hover);
}

.project-description-deltma {
    position: absolute;
    bottom: -40%;
    left: 10%;
    width: 20%;
    margin-left: 15px;
    letter-spacing: 2px;
    text-align: center;
    font-size: 16px;
    color: white;
    z-index: -2;
    pointer-events: none;
}

.project-description-worldwidepancakes {
    position: absolute;
    bottom: -45%;
    right: -55%;
    margin-right: 10px;
    width: 100%;
    transform: translate(-50%, -50%);
    letter-spacing: 2px;
    font-size: 16px;
    color: white;
    z-index: -2;
    pointer-events: none;
}

a:visited,
a:link {
    color: var(--orange);
    text-decoration: none;
}

.link-to-repo-intranet a,
.link-to-repo-worldwidepancakes a {
    position: absolute;
    bottom: -50%;
    left: 20%;
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
    z-index: -2;
}

.link-to-repo-worldwidepancakes {
    position: absolute !important;
    left: 50% !important;
    bottom: -70% !important;
}

.project-video {
    position: absolute;
    bottom: -45%;
    right: -5%;
    margin-right: 50px;
    transform: translate(-50%, -50%);
    transition: transform 1s;
}

.project-video video {
    max-width: 400px;
    border: 1px solid #333333;
    border-radius: 5%;
    opacity: 0.4;
    transition: transform 0.8s ease-in-out, opacity 0.8s ease-in-out;
}

.project-video video:hover {
    opacity: 1;
    transform: scale(1.75);

}

.project-video:hover .overlay-text {
    transform: scale(1.5);
    opacity: 0;
}
</style>