<template>
    <div class="project">
        <div class="project-image" :class="{ 'expanded': isImageExpanded }" @mouseleave="handleMouseLeave"
            @mouseover="expandImage">
            <img :src="currentImage" alt="project-image">
            <div class="overlay-text">Web Shop Development</div>
            <div class="project-description">
                An online platform for browsing and purchasing products with a user-friendly interface.
            </div>
            <div class="navigation-buttons">
                <button class="previous-button" @click="navigate('previous')">Previous</button>
                <button class="next-button" @click="navigate('next')">Next</button>
            </div>
        </div>
        <div class="link-to-repo">
            <a href="https://github.com/dzJP/webshop">Repository</a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            images: [
                require('@/assets/webshop/login.png'),
                require('@/assets/webshop/register.png'),
                require('@/assets/webshop/resetPassword.png'),
                require('@/assets/webshop/adminpage.png'),
                require('@/assets/webshop/adminpageCreateProduct.png'),
                require('@/assets/webshop/adminpageEditProduct.png'),
                require('@/assets/webshop/adminpageDeleteProduct.png'),
                require('@/assets/webshop/userPage.png'),
                require('@/assets/webshop/addToCart.png'),
                require('@/assets/webshop/cartPopup.png'),
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
        expandImage() {
            this.isImageExpanded = true;
        },
        handleMouseLeave(event) {
            const expandedImage = document.querySelector('.project-image.expanded');
            if (expandedImage && !expandedImage.contains(event.relatedTarget)) {
                this.isImageExpanded = false;
            }
        },
        navigate(direction) {
            if (direction === 'previous') {
                this.currentImageIndex = (this.currentImageIndex - 1 + this.images.length) % this.images.length;
            } else if (direction === 'next') {
                this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
            }
        },
    },
};
</script>
