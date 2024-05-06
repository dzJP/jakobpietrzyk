<template>
    <div class="project-section-container">
        <div class="project-section-title">My projects</div>
        <div class="projects">
            <div class="project">
                <div class="project-image" :class="{ 'expanded': isImageExpanded }" @mouseleave="handleMouseLeave" @mouseover="expandImage">
                    <img :src="currentImage" alt="project-image">
                    <div class="overlay-text" v-if="!isImageExpanded">Intranet development</div>
                    <div class="project-description" v-if="!isImageExpanded">
                        A secure and efficient internal network for streamlined communication, collaboration, and
                        information
                        sharing.
                    </div>
                    <div class="navigation-buttons">
                        <button class="button" @click="navigate('previous')">Previous</button>
                        <button class="button" @click="navigate('next')">Next</button>
                    </div>
                </div>
                <div class="link-to-repo">
                    <a href="https://github.com/dzJP/intranet">Repository</a>
                </div>
            </div>
            <div class="project">
                <div class="project-video">
                    <video controls>
                        <source src="@/assets/worldwidepancakes.mp4" type="video/mp4">
                        Your browser does not support the video tag.
                    </video>
                    <div class="overlay-text" v-if="!isImageExpanded">World Wide Pancakes</div>
                    <div class="project-description" v-if="!isImageExpanded">
                        World Wide Pancakes is a web app where pancake enthusiasts can discover, share, and connect over
                        delicious
                        recipes.
                    </div>
                </div>
                <div class="link-to-repo">
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
};
</script>
<style>
.project-section-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    min-height: 600px;
    background-color: var(--darkest-gray-black);
    border-top: 2px solid var(--orange);
}

.project-section-title {
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
    justify-content: space-between;
    align-items: flex-end;
    padding: 20px;
    width: 75%;
    padding: 5%;
}

.project {
    position: relative;
    z-index: 1;
}

.project-image img,
.project-video video {
    width: 400px;
    border: 2px solid var(--dark-gray-black);
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

.project-image:hover .overlay-text,
.project-video:hover .overlay-text {
    opacity: 0;
    transform: scale(1.5);
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
    transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
}

.project-image:hover .overlay-text {
    opacity: 0;
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

.project-image.expanded:hover .navigation-buttons {
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
    height: 50px;
    padding: 4px 20px;
    margin-right: 10px;
    cursor: pointer;
    transition: background-color 0.5s ease;
}

.navigation-buttons .button:hover {
    background-color: var(--light-blue-hover);
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
</style>
