<template>
    <header class="head-container">
        <div id="home" class="head-portfolio-text">
            Portfolio
        </div>
            <DropdownComponent />
    </header>

</template>

<script>
import DropdownComponent from '@/components/DropdownComponent';

export default {
    components: {
        DropdownComponent
    }
}

</script>
<style>

.head-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: var(--light-gray);
    height: 70px;
    border-bottom: 2px solid var(--lighter-gray);
    z-index: 1000;
}

.head-portfolio-text {
    display: flex;
    justify-content: flex-end;
    margin: 15px 35px 10px;
    font-weight: 600;
    font-size: 2em;
    letter-spacing: 6px;
    text-transform: uppercase;
}

@media (max-width: 360px) {
    
    .head-container {
        border-bottom: 2px solid var(--lighter-gray) !important;
    }
}
</style>