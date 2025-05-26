<template>
    <section id="hero" class="hero-section">
        <div class="overlay fade-up">
            <div class="content">
                <h1>Глеб Панченко</h1>
                <h2>Unity Developer</h2>
                <div class="scroll" @click="scrollToNext">
                    <svg style="fill:#fff;" width="38.417px" height="18.592px"
                        viewBox="0 0 38.417 18.592">
                        <path
                            d="M19.208,18.592c-0.241,0-0.483-0.087-0.673-0.261L0.327,1.74c-0.408-0.372-0.438-1.004-0.066-1.413c0.372-0.409,1.004-0.439,1.413-0.066L19.208,16.24L36.743,0.261c0.411-0.372,1.042-0.342,1.413,0.066c0.372,0.408,0.343,1.041-0.065,1.413L19.881,18.332C19.691,18.505,19.449,18.592,19.208,18.592z" />
                    </svg>
                </div>
            </div>
        </div>
    </section>
    <section ref="nextSection" id="about" class="about-section">
        <div class="about-content">
            <div class="state fade-up">
                <img src="@/assets/avatar.jpg" alt="Глеб Панченко" class="avatar" />
                <div class="text fade-up">
                    <h2>Глеб Панченко</h2>
                    <p class="experience">Опыт разработки в Unity — 2+ года</p>
                </div>
            </div>
            <p class="intro">
                Привет! Вы находитесь на странице моего портфолио. Здесь я демонстрирую результаты своего опыта
                разработки игр и приложений с использованием C#, Unity и VR-технологий.
            </p>
        </div>

        <div class="tech-section">
            <h3>Кратко о себе</h3>
            <p>
                Разрабатываю игры и VR-приложения на Unity с 2022 года.<br/>
                Специализируюсь на игровых механика и архитектуре проектов.<br/>
                Руководил командами до 7 человек и вел проекты с нуля до продакшена.
            </p>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

const nextSection = ref(null)

const scrollToNext = () => {
    nextSection.value?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<style scoped>
.hero-section {
    height: 100vh;
    background: url('@/assets/preview.jpg') center center / cover no-repeat;
    margin: 0;
    padding: 20px;
    position: relative;
    overflow: hidden;
}

.overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    align-items: center;
    justify-content: center;
}

.content {
    color: #fff;
    text-align: center;
    max-width: 90%;
}

h1 {
    font-size: 3rem;
    margin-bottom: 0.5rem;
}

h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    font-weight: 300;
}

p {
    font-size: 1.2rem;
    margin-bottom: 1.5rem;
}

.contacts a {
    margin: 0 1rem;
    color: #8fbc83;
    text-decoration: underline;
}

@keyframes t-arrow-bottom {
    0% {
        transform: translateY(0px);
    }

    50%,
    55% {
        transform: translateY(-7px);
    }

    100% {
        transform: translateY(0px);
    }
}

.scroll {
    align-items: center;
    position: absolute;
    bottom: 4vh;
    left: 49%;
    transform: translateX(-0vh);
    cursor: pointer;
    animation: t-arrow-bottom 3s infinite ease;
}

.next-section {
    height: 100vh;
    background-color: #1e1e1e;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
}

.about-section {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px;
    color: #222;
}

.about-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 50px;
}

.state {
    display: flex;
    align-items: center;
    justify-content: start;
    text-align: center;
    gap: 1rem;
    margin-bottom: 1rem;
}

.avatar {
    width: 10em;
    height: 10em;
    border-radius: 50%;
    object-fit: cover;
}


.text h2 {
    background-color: #8fbc83;
    padding-left: .3rem;
    font-size: 1.8rem;
    margin-bottom: 0.3rem;
}

.experience {
    font-size: 1rem;
    color: #666;
}

.intro {
    text-align: center;
    font-size: 1.1rem;
    max-width: 600px;
    margin-top: 1rem;
}

.tech-section {
    text-align: center;
}

.tech-section h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
}

.tech-section p {
    background-color: #8fbc83;
    max-width: 700px;
    padding: .5rem;
    font-size: 1rem;
    color: #444;
}
</style>
