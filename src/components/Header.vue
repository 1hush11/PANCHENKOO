<template>
    <nav class="site-nav">
        <div class="nav-container fade-up">
            <div class="burger" @click="toggleMenu">
                ☰
            </div>

            <ul :class="['nav-links', { open: isOpen }]">
                <li><a href="#hero" @click="closeMenu">В начало</a></li>
                <li><a href="#about" @click="closeMenu">Знакомство</a></li>
                <li><a href="#projects" @click="closeMenu">Проекты</a></li>
                <li><a href="#details" @click="closeMenu">Обо мне</a></li>
            </ul>
        </div>
    </nav>
</template>


<script setup>
import { ref } from 'vue'

const isOpen = ref(false)

const toggleMenu = () => {
    isOpen.value = !isOpen.value
}

const closeMenu = () => {
    isOpen.value = false
}
</script>


<style scoped>
.site-nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: rgba(17, 17, 17, 0.95);
    color: #fff;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.4);
}

.nav-container {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 1rem 2rem;
    max-width: 1200px;
    margin: auto;
}

.nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
    transition: transform 0.3s ease;
}
.nav-links a {
    color: #8fbc83;
    text-decoration: none;
    font-weight: 600;
    font-family: "Exo 2", sans-serif;
}
.nav-links a:hover {
    color: #ffffff;
}

.burger {
    display: none;
    font-size: 1.5rem;
    cursor: pointer;
    user-select: none;
}

@media (max-width: 768px) {
    .burger {
        display: block;
        margin-left: auto;
    }

    .nav-links {
        position: absolute;
        top: 64px;
        left: 0;
        width: 100%;
        background: rgba(17, 17, 17, 0.95);
        flex-direction: column;
        gap: 1rem;
        padding: 1rem 2rem;
        transform: translateY(-200%);
        opacity: 0;
        pointer-events: none;
        align-items: flex-end;
    }

    .nav-links.open {
        transform: translateY(0);
        opacity: 1;
        pointer-events: all;
    }
    .nav-links a:hover {
        color: #ffffff;
    }
}
</style>
