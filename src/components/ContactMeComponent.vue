<template>
    <div id="contact" class="contact-container">
        <div class="contact-me-header">
            Contact me
        </div>
        <form id="contactForm" class="contact-form" @submit.prevent="submitForm">
            <div class="input-box">
                <input type="text" name="fullName" id="fullName" placeholder="Namn">
                <input type="email" name="emailAddress" id="emailAddress" placeholder="E-postadress">
            </div>
            <div class="input-box">
                <input type="tel" name="number" placeholder="Mobilnummer" pattern="[+]?[0-9]+(\.[0-9]{1,2})?">
                <input type="text" name="emailSubject" placeholder="Subject">
            </div>
            <div class="input-box">
                <textarea name="emailMessage" id="" cols="30" rows="10" placeholder="Your message"></textarea>
            </div>
            <input type="submit" value="Submit" class="btn" name="send">
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            formData: {
                name: '',
                email: '',
                message: ''
            }
        };
    },
    methods: {
        submitForm() {
            console.log('Form submitted:', this.formData);
            this.formData = {
                name: '',
                email: '',
                message: ''
            };
        }
    }
};
</script>
<style>
.contact-container {
    min-height: 100vh;
    padding: 10rem 9% 2rem;
    border-top: solid 1px var(--lightest-gray);
}

.contact-me-header {
    text-align: center;
    text-transform: uppercase;
    font-family: 'Oxanium', sans-serif;
    letter-spacing: 5px;
    font-size: 40px;
    color: var(--white);
}

.contact-form {
    max-width: 55rem;
    margin: 1rem auto;
    text-align: center;
    margin-bottom: 3rem;

}

.input-box {
    display: flex;
    justify-content: center;
    margin-bottom: 1.5rem;
}

.input-field,
.textarea-field {
    flex: 1;
    padding: 0.5rem;
    font-size: 1rem;
    border-radius: 4px;
}

.input-box input[type="text"],
.input-box input[type="email"],
.input-box input[type="tel"],
.input-box textarea {
    flex: 1;
    padding: 0.5rem;
    font-size: 1rem;
    margin: 5px 15px 5px;
    border: 2px solid var(--light-gray);
    border-radius: 10px;
    background-color: var(--lightest-gray);
    height: 40px;
    font-family: 'Oxanium', sans-serif;
    color: var(--white);
}

.input-box textarea {
    height: 200px;
}

.btn {
    padding: 0.5rem 2rem;
    font-size: 1rem;
    background-color: var(--light-blue);
    color: var(--white);
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
    font-family: 'Oxanium', sans-serif;
    text-transform: uppercase;
    letter-spacing: 2px;
    box-shadow: 0 0 1rem var(--light-blue-hover);
}

.btn:hover {
    background-color: var(--light-blue-hover);
}
</style>