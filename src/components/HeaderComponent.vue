<template>
    <div id="home" class="header-container">
        <div class="header-role">
            Java Full Stack Developer
        </div>
        <div class="header-name">
            Jakob Pietrzyk
        </div>
    </div>
    <!-- <div class="profile-picture">
    <img src="@/assets/jakob.jpg" alt="profile-picture">
    </div> -->
</template>

<style>
.header-container {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-top: 5%;
    padding-bottom: 30px;
    min-height: 200px;
    border-bottom: solid 1px var(--light-gray);
}

.header-role {
    position: absolute;
    right: -5%;
    top: 25%;
    transform: translate(-50%, -50%);
    font-size: 25px;
    letter-spacing: 5px;

}

.header-name {
    position: absolute;
    right: 5%;
    top: 35%;
    font-size: 60px;
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
</style>