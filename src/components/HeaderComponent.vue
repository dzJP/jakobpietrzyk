<template>
    <section class="home">
        <div class="home-content">
            <div class="header-text">
                {{ typedText }}
                <span class="cursor" :class="{ 'blink': showCursor }"></span>
            </div>
            <div class="header-name">
                Jakob Pietrzyk
            </div>
        </div>
        <div class="profile-picture">
            <img src="@/assets/jakob.jpg" alt="profile-picture" class="profile-img">
        </div>
    </section>
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
                    }, 1000);
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
.home {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    border-bottom: solid 1px var(--lightest-gray);
}

.header-content {
    position: absolute;
    text-align: center;
}

.header-name {
    font-size: 3em;
    text-transform: uppercase;
    letter-spacing: 10px;
}

.header-text {
    font-size: 1.5em;
    letter-spacing: 2px;
    margin-left: 5px;
    color: var(--white);
}

.profile-picture {
    margin-left: 15em;
    animation: fadeIn 2s ease forwards, floatLeftRight 15s linear infinite;
}

.profile-img {
    max-width: 300px;
    border-radius: 10%;
    transform: scaleX(-1);
}

.cursor {
    border-right: 4px solid var(--blue-heaven);
    font-size: 1.2em;
}

.blink {
    animation: blink-animation 1s infinite;
}
@keyframes fadeIn {
    0% {
        opacity: 0;
        transform: translateX(-100%);
    }
    100% {
        opacity: 1;
        transform: translateX(0);
    }
}

@keyframes floatLeftRight {
    0% {
        transform: translateX(5px);
    }
    50% {
        transform: translateX(-5px);
    }
    100% {
        transform: translateX(5px);
    }
}

@keyframes blink-animation {
    0% { opacity: 1; }
    50% { opacity: 0; }
    100% { opacity: 1; }
}

@media (max-width: 1366px) {
    .home {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 100px;
        
    }
    .header-name {
        font-size: 2em;
        white-space: nowrap;
        letter-spacing: 10px;
    }

    .header-text {
        font-size: 1em;
        letter-spacing: 4px;
        white-space: nowrap;
    }
    .profile-picture {
        margin-left: -5%;
    }
    .profile-img {
        max-width: 200px;
        border-radius: 10%;
    }
}
/* @media (max-width: 768px) {
    .home {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 100px;
    }
    .header-name {
        font-size: 2em;
        white-space: nowrap;
        letter-spacing: 10px;
    }

    .header-text {
        font-size: 1em;
        letter-spacing: 4px;
        white-space: nowrap;
    }
    .profile-picture {
        margin-left: -5%;
    }
    .profile-img {
        max-width: 200px;
        border-radius: 10%;
    }
} */
/* @media (max-width: 320px) {
    .header-name {
        position: absolute;
        top: 28%;
        left: 10px;
        translate: transform(-50%, -50%);
        font-size: 1.2em;
        font-weight: 700;
        line-height: 5;
    }
    .header-text {
        position: absolute;
        top: 25%;
        left: 7px;
        font-size: 0.9em;
        translate: transform(-50%, -50%);
    
    }
    .profile-picture {
        position: absolute;
        top: 50%;
        right: 25%;
        translate: transform(-50%, -50%);
    }
    .profile-img {
        max-width: 10em;

    }
} */
@media (max-width: 360px) {
    .home {
    }
    .header-name {
        position: absolute;
        top: 40%;
        left: 0.5em;
        translate: transform(-50%, -50%);
        font-size: 1.8em;
        letter-spacing: 8px;
        font-weight: 400;
    }
    .header-text {
        position: absolute;
        top: 35%;
        left: 13px;
        font-size: 1.1em;
        translate: transform(-50%, -50%);
        font-weight: 400;
        letter-spacing: 5px;
        line-height: 1.2;
    }
    .profile-picture {
        position: absolute;
        top: 50%;
        right: 25%;
        translate: transform(-50%, -50%);
    }
    .profile-img {
        max-width: 10em;

    }
}
</style>