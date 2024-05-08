<template>
    <section class="about" id="about">
        <div class="about-img" alt="about-img">
            <img src="@/assets/imgcode.jpg">
        </div>
        <div class="about-content">
            <h2 class="heading">
                <span>About me</span>
            </h2>
            <h3>
                {{ typedText }}
                <span class="cursor" :class="{ 'blink': showCursor }"></span>
            </h3>
            <p>
                I'm a dedicated and highly motivated Java programmer with a strong background in Java programming, database development, and web development.
                Skilled in Java, JavaScript, and proficient in utilizing a diverse array of frameworks and tools.
				With a desire to learn, I'm always seeking for opportunities to expand my existing knowledge and skill set.
            </p>
            <a href="#contact" class="button">Contact me</a>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            messages: [
                "Hi, I'm Jakob.",
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
.about {
    background-color: var(--light-gray);
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 4rem;
}

.about-content h2 {
    display: flex;
    flex-direction: row;
    justify-content: center;
    font-size: 2.6em;
    font-weight: 700;
    margin: 2rem 2% 9rem;
    animation: fadeInFromRight 2s ease forwards;
}

.about-content h3 {
    color: var(--white);
    font-size: 2rem;
    font-weight: 600;
    letter-spacing: 2px;
}

.about-content p {
    font-size: 1.2rem;
    letter-spacing: 2px;
    margin: 2rem 0 3rem;
    color: var(--white);
    animation: fadeInFromBottom 2s ease forwards;
}

.about-img img {
    max-width: 600px;
    border-radius: 10%;
    animation: fadeInFromLeft 2s ease forwards;
}

span {
    color: var(--white);
    letter-spacing: 5px;
    font-size: 1em;
}

.blink {
    animation: blink-animation 1s infinite;
}

.button {
    animation: buttonFadeIn 5s ease forwards;
}

@keyframes buttonFadeIn {
    0% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}

@keyframes blink-animation {
    0% {
        opacity: 1;
    }

    50% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}

@keyframes fadeInFromLeft {
    0% {
        opacity: 0;
        transform: translateX(-50%);
    }

    100% {
        opacity: 1;
        transform: translateX(0);
    }
}

@keyframes fadeInFromBottom {
    0% {
        opacity: 0;
        transform: translateY(100%);
    }

    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes fadeInFromTop {
    0% {
        opacity: 0;
        transform: translateY(-100%);
    }

    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes fadeInFromRight {
    0% {
        opacity: 0;
        transform: translateX(50%);
    }

    100% {
        opacity: 1;
        transform: translateX(0);
    }
}

@media (max-width: 1366px) {
    .about {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .about-content h2 {
        display: flex;
        flex-direction: row;
        justify-content: center;
        font-size: 2em;
        font-weight: 700;
        animation: none !important;
        font-family: 'Oxanium', sans-serif;
    }

    .about-content h3 {
        font-family: 'Oxanium', sans-serif;
        color: var(--white);
        font-size: 1.2rem;
        font-weight: 600;
        letter-spacing: 2px;
    }

    .about-content p {
        font-size: 1.2rem;
        letter-spacing: 2px;
        margin: 2rem 0 3rem;
        color: var(--white);
        font-family: 'Oxanium', sans-serif;
        
    }
    .about-img {
        width: 100%;
        height: 100%;
        overflow: hidden;
        
    }
    .about-img img {
        width: 100%;
        height: 100px;
        display: block;
        object-fit: cover;
        object-position:left;
        border-radius: 0;
        animation: none !important;
    }
}
</style>