<template>
    <div class="project">
        <div class="project-image" :class="{ 'expanded': isImageExpanded }" @mouseleave="handleMouseLeave"
            @mouseover="expandImage">
            <img :src="currentImage" alt="project-image">
            <div class="overlay-text" v-if="!isImageExpanded">Intranet development</div>
            <div class="project-description" v-if="!isImageExpanded">
                A secure and efficient internal network for streamlined communication, collaboration, and information
                sharing.
            </div>
            <div class="navigation-buttons">
                <button class="previous-button" @click="navigate('previous')">Previous</button>
                <button class="next-button" @click="navigate('next')">Next</button>
            </div>
        </div>
        <div class="link-to-repo">
            <a href="https://github.com/dzJP/intranet">Repository</a>
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
        toggleImageSize(event) {
            if (event.target.tagName.toLowerCase() === 'img') {
                this.isImageExpanded = !this.isImageExpanded;
                const overlayText = document.querySelector('.overlay-text');
                if (overlayText) {
                    overlayText.style.display = this.isImageExpanded ? 'none' : 'block';
                }
            }
        },
        navigate(direction) {
            if (direction === 'previous') {
                this.currentImageIndex = (this.currentImageIndex - 1 + this.images.length) % this.images.length;
            } else if (direction === 'next') {
                this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
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