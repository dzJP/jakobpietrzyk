<template>
    <div class="header-container">
        <div class="header-text">
            {{ typedText }}
            <span class="cursor" :class="{ 'blink': showCursor }"></span>
        </div>
        <div class="header-name">
            Jakob Pietrzyk
        </div>
    </div>
    <!-- <div class="profile-picture">
        <img src="@/assets/jakob.jpg" alt="profile-picture">
    </div> -->
</template>

<script>
export default {
    data() {
        return {
            messages: [
                "Java Full Stack Developer",
                "Frontend Developer",
                "Backend Developer"
            ],
            currentMessageIndex: 0,
            typedText: "",
            typingSpeed: 100,
            showCursor: true,
            typingDirection: 1, // 1 for left to right, -1 for right to left
        };
    },
    mounted() {
        this.typeText();
    },
    methods: {
        typeText() {
            const currentMessage = this.messages[this.currentMessageIndex];
            let index = (this.typingDirection === 1) ? 0 : currentMessage.length;
            const typingInterval = setInterval(() => {
                if ((this.typingDirection === 1 && index <= currentMessage.length) ||
                    (this.typingDirection === -1 && index >= 0)) {
                    this.typedText = currentMessage.slice(0, index);
                    index += this.typingDirection;
                } else {
                    clearInterval(typingInterval);
                    setTimeout(() => {
                        this.eraseText();
                    }, 2000);
                }
            }, this.typingSpeed);
        },
        eraseText() {
            let index = (this.typingDirection === 1) ? this.typedText.length : 0;
            const erasingInterval = setInterval(() => {
                if ((this.typingDirection === 1 && index >= 0) ||
                    (this.typingDirection === -1 && index <= this.typedText.length)) {
                    this.typedText = this.typedText.slice(0, index);
                    index -= this.typingDirection;
                } else {
                    clearInterval(erasingInterval);
                    this.currentMessageIndex = (this.currentMessageIndex + 1) % this.messages.length;
                    setTimeout(() => {
                        this.typeText();
                    }, 2000);
                }
            }, this.typingSpeed);
        },
    },
}
</script>

<style>
.header-container {
    margin-top: 15%;
    min-height: 100px;
    border-bottom: solid 1px var(--lightest-gray);
}

.header-name {
    position: absolute;
    top: 20%;
    left: 30%;
    transform: translate(-50%, -50%);
    font-size: 3em;
    text-transform: uppercase;
    letter-spacing: 10px;
}

.profile-picture {
    position: absolute;
    top: 5%;
    left: 5%;
}

.profile-picture img {
    max-width: 200px;
    border: 2px solid #333333;
    border-radius: 50%;
}

.header-text {
    position: absolute;
    left: 20%;
    top: 25%;
    font-size: 1.5em;
    letter-spacing: 2px;
}

.cursor {
    border-right: 4px solid var(--blue-heaven);
    height: 1.5em;
    font-family: 'Oxanium', sans-serif;
}

.blink {
    animation: blink-animation 1s infinite;

}

@keyframes blink-animation {
    0% { opacity: 1; }
    50% { opacity: 0; }
    100% { opacity: 1; }
}
</style>
