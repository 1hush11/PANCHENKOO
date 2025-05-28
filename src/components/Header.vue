<template>
    <nav class="site-nav">
        <div class="nav-container fade-up">
            <div class="burger" :class="{ open: isOpen }" @click="toggleMenu">
                <svg width="28" height="28" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M4 7a1 1 0 0 1 1-1h14a1 1 0 1 1 0 2H5a1 1 0 0 1-1-1zm0 5a1 1 0 0 1 1-1h14a1 1 0 1 1 0 2H5a1 1 0 0 1-1-1zm0 5a1 1 0 0 1 1-1h14a1 1 0 1 1 0 2H5a1 1 0 0 1-1-1z" fill="#CCC"/>
                </svg>
            </div>

            <ul :class="['nav-links', { open: isOpen }]">
                <li><a @click="closeMenu" @click.prevent="scrollToSection('hero')">В начало</a></li>
                <li><a @click="closeMenu" @click.prevent="scrollToSection('about')">Знакомство</a></li>
                <li><a @click="closeMenu" @click.prevent="scrollToSection('projects')">Проекты</a></li>
                <li><a @click="closeMenu" @click.prevent="scrollToSection('details')">Обо мне</a></li>
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

const scrollToSection = (id) => {
    const el = document.getElementById(id)
    if (el) {
        el.scrollIntoView({ behavior: 'smooth' })
    }
}
</script>


<style scoped>
.site-nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: rgba(17, 17, 17, 0.95);
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.4);
    cursor: pointer;
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
    color: #CCC;
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
    transition: transform 0.3s ease;
}
.burger.open {
    transform: scale(1.5);
}

@media (max-width: 768px) {
    .nav-container {
        position: relative; 
        justify-content: flex-end;
    }

    .burger {
        display: block;
        height: 28px;
        margin: 0;
        align-items: flex-end;
    }

    .nav-links {
        position: relative;
        top: auto;
        left: auto;
        right: 0;
        width: 100%;
        flex-direction: column;
        align-items: flex-end;
        gap: 1rem;
        padding: 1rem 2rem;
        margin-top: 0.5rem;

        opacity: 0;
        max-height: 0;
        overflow: hidden;
        transition: max-height 0.3s ease;
    }

    .nav-links.open {
        max-height: 300px;
        padding: 1rem 2rem;
        opacity: 1;
    }
    .nav-links a:hover {
        color: #ffffff;
    }
}
</style>
