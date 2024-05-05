<template>
    <div class="header-container">
        <div class="header-role">
            Java Full Stack Developer
        </div>
        <div class="header-name">
            Jakob Pietrzyk
        </div>
    </div>
    <div class="profile-picture">
        <img src="@/assets/jakob.jpg" alt="profile-picture">
    </div>
</template>

<style>
.header-container {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-top: 5%;
    padding-bottom: 5px;
    margin-left: 50%;
}

.header-role {
    position: relative;
    display: flex;
    top: 5%;
    font-size: 25px;
    letter-spacing: 5px;

}

.header-name {
    font-size: 60px;
    text-transform: uppercase;
    letter-spacing: 10px;
    padding-bottom: 15px;
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
</style>