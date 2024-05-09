<template>
    <div class="head-container">
        <div class="head-portfolio-text">
            Portfolio
        </div>
        <DropdownComponent />
    </div>

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
    margin: 20px 20px 5px;
    font-weight: 600;
    font-size: 26px;
    letter-spacing: 5px;
    text-transform: uppercase;
}
</style>