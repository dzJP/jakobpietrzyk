<template>
    <div id="contact" class="contact-container">
        <div class="contact-me-header">
            Contact me
        </div>
        <form id="contactForm" class="contact-form" @submit.prevent="submitForm">
            <div class="input-box">
                <input v-model="formData.name" :disabled="isSubmitting" type="text" name="fullName" id="fullName" placeholder="Name">
                <input v-model="formData.email" :disabled="isSubmitting" type="email" name="emailAddress" id="emailAddress" placeholder="E-mail">
            </div>
            <div class="input-box">
                <input v-model="formData.phoneNumber" :disabled="isSubmitting" type="tel" name="number" placeholder="Phonenumber" pattern="[+]?[0-9]+(\.[0-9]{1,2})?">
                <input v-model="formData.subject" :disabled="isSubmitting" type="text" name="emailSubject" placeholder="Subject">
            </div>
            <div class="input-box">
                <textarea v-model="formData.message" :disabled="isSubmitting" name="emailMessage" cols="30" rows="10" placeholder="Message"></textarea>
            </div>
            <input :disabled="isSubmitting" type="submit" :class="{'btn': true, 'btn-disabled': isSubmitting}" value="Submit" name="send">
        </form>
    </div>
</template>

<script>
import axios from "axios";

export default {
    data() {
        return {
            formData: {
                name: '',
                email: '',
                phoneNumber: '',
                subject: '',
                message: ''
            },
            isSubmitting: false
        };
    },
    methods: {
        async submitForm() {
            this.isSubmitting = true;
            console.log('Form submitted:', this.formData);
            try {
                const response = await axios.post(
                    'https://portfolio-jakob.azurewebsites.net/api/v1/submitContactForm',
                    this.formData
                );
                console.log('Server response:', response.data);
                // Handle successful submission logic here if needed
            } catch (error) {
                console.error('Error submitting form:', error);
                // Handle the error if needed
            }
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
    color: var(--white);
}

.input-box textarea {
    height: 200px;
}

.btn {
    display: inline-block;
    font-size: 1.2em;
    font-family: 'Oxanium', sans-serif;
    font-weight: 600;
    text-align: center;
    text-transform: uppercase;
    text-decoration: none;
    letter-spacing: 4px;
    background-color: var(--blue-sky);
    color: var(--white);
    padding: 10px 20px;
    border-radius: 5px;
    border: none;
    transition: background-color 0.5s ease;
    box-shadow: 0 0 1rem var(--blue-heaven-hover);
    cursor: pointer;
}

.btn:hover {
    background-color: var(--blue-sky-hover);
}

.btn-disabled {
    background-color: var(--light-gray);
    cursor: not-allowed;
}

@media (max-width: 360px) {
    .contact-container {
        padding: 10rem 5% 2rem;
    }
    .contact-form {
        max-width: 90%;
        margin-top: 30%;
    }
    .input-box {
        flex-direction: column;
        margin-bottom: 1rem;
    }
    .input-box input[type="text"],
    .input-box input[type="email"],
    .input-box input[type="tel"],
    .input-box textarea {
        margin: 5px 0;
        width: 100%;
    }
    .btn {
        padding: 0.5rem 1rem;
        font-size: 1rem;
        margin-top: 1rem;
        display: inline-block;
        font-weight: 600;
        text-align: center;
        text-transform: uppercase;
        text-decoration: none;
        letter-spacing: 3px;
        background-color: var(--blue-sky);
        border-radius: 5px;
        border: none;
        transition: background-color 0.5s ease;
        box-shadow: 0 0 1rem var(--blue-heaven-hover);
    }
}
</style>
