<template>
    <section id="projects" class="projects-section fade-up">
        <div
            v-for="(project, index) in projects"
            :key="index"
            class="project"
        >
            <div
                class="project-content"
                :class="getProjectClass(project.title)"
            >
                <h3 class="project-title">{{ project.title }}</h3>

                <div class="columns">
                    <div class="project-info">
                        <p class="project-p"><strong class="strong">Роль:</strong> {{ project.role }}</p>
                        <p class="project-p"><strong class="strong">Длительность проекта:</strong> {{ project.duration }}</p>
                        <p class="description">
                            <strong>Описание: </strong>{{ project.description }}
                        </p>
                        <p class="project-p"><strong class="strong">Технологии:</strong> {{ project.technologies }}</p>
                        <p class="project-p" v-if="project.link">
                            <strong>Ссылка на проект: </strong>
                            <a class="link" :href="project.link" target="_blank">{{ formatLink(project.link) }}</a>
                        </p>
                    </div>

                    <div class="project-gallery" v-if="project.images && project.images.length">
                        <img :src="project.preview" class="preview-image" alt="preview" />
                    </div>
                </div>
            </div>

            <div class="carousel-section" v-if="project.images.length > 1">
                <div
                    class="slider-wrapper"
                    @touchstart.passive="onTouchStart($event, index)"
                    @touchmove.passive="onTouchMove($event, index)"
                    @touchend.passive="onTouchEnd($event, index)"
                >
                    <button class="arrow left" @click="prevSlide(index)">‹</button>
                    <div class="slider">
                        <transition name="fade" mode="out-in">
                            <img
                                :src="project.images[project.currentIndex]"
                                :key="project.currentIndex"
                                class="slide"
                            />
                        </transition>
                    </div>
                    <button class="arrow right" @click="nextSlide(index)">›</button>
                </div>

                <div class="dots">
                    <span
                        v-for="(img, i) in project.images"
                        :key="i"
                        :class="{ dot: true, active: i === project.currentIndex }"
                        @click="goToSlide(index, i)"
                    ></span>
                </div>
            </div>
        </div>
    </section>
</template>


<script setup>
import { reactive } from 'vue'

const projects = reactive([
    {
        title: 'VR – кинотеатр',
        duration: '6 месяцев',
        description: "VR-приложение для просмотра видеоконтента в виртуальном пространстве. Поддерживаются режимы 180° и 360°, а также полноценное управление медиатекой. Реализован оффлайн-доступ к видеофайлам для использования без подключения к интернету. Данные пользователей и контент защищены с помощью системы шифрования. Приложение построено на клиент-серверной архитектуре с авторизацией и сбором статистики. Оптимизировано под VR-устройства, включая устаревшую платформу Oculus Go.",
        role: 'Unity-разработчик',
        technologies: 'URP, Figma, AVPro, REST API, JSON, Swagger, Unity Profiler',
        link: 'https://altairika.com/',
        preview: '/assets/altairika-preview.jpg',
        images: [
            '/assets/altairika1.jpg',
            '/assets/altairika2.jpg',
            '/assets/altairika3.jpg',
        ],
        currentIndex: 0,
    },
    {
        title: 'СИТ-НЕБО',
        duration: '12 месяцев',
        description: "VR-симулятор управления беспилотниками мультироторного, самолетного и наземного типов. В проекте реализован широкий набор одиночных заданий, включая классические режимы: свободный полёт, гонки и полет по кольцам. Также доступны специализированные миссии для развития навыков, востребованных в промышленности.\nПоддерживается сетевой режим, позволяющий соревноваться с другими пользователями. Предусмотрена настройка специализированных джойстиков для точного управления. Встроены редакторы карт и дронов, что позволяет создавать уникальные сценарии и конфигурации.",
        role: 'Team Lead',
        technologies: 'HDRP, Figma, Mirror, Rewired, Asset Bundles, Shader Graph, HLSL, WebSockets, TCP, REST API, JSON, Swagger, FMOD, Cinemachine, I2 Localization, Unity Profiler',
        link: 'https://sit-nebo.ru/',
        preview: '/assets/sit-preview.jpg',
        images: [
            '/assets/sit1.jpg',
            '/assets/sit2.jpg',
            '/assets/sit3.jpg',
            '/assets/sit4.jpg',
            '/assets/sit5.jpg',
            '/assets/sit6.jpg',
        ],
        currentIndex: 0,
    },
    {
        title: 'Конструктор ванных комнат',
        duration: '5 месяцев',
        description: "Приложение для сотрудников торговых сетей, позволяющее проектировать ванные комнаты с учётом индивидуальных пожеланий клиента. Интерактивный конструктор обеспечивает удобное размещение объектов с возможностью задания размеров, материалов и цветовых решений. \nГотовые проекты автоматически сохраняются на сервере и доступны для дальнейшей модерации. Реализована генерация технической документации для производства и возможность отправки проекта с сопроводительной информацией на электронную почту клиента. Дополнительный функционал включает отображение размеров изделий и переключение режимов камеры для удобного обзора сцены.",
        role: 'Team Lead',
        technologies: 'HDRP, Figma, Zenject, MVC, Addressables, Event Aggregator, REST API, JSON, Swagger',
        link: 'https://kupalapro.ru/',
        preview: '/assets/kupala-preview.jpg',
        images: [
            '/assets/kupala1.png',
            '/assets/kupala2.png',
            '/assets/kupala3.png',
            '/assets/kupala4.png',
            '/assets/kupala5.png',
            '/assets/kupala6.png',
            '/assets/kupala7.png',
        ],
        currentIndex: 0,
    },
])

function getProjectClass(title) {
    if (title.includes('СИТ-НЕБО')) return 'sit-nebo'
    if (title.includes('ванных')) return 'kupala'
    if (title.includes('VR – кинотеатр')) return 'altairika'
    return ''
}

function formatLink(url) {
    return url
    .replace(/^https?:\/\/(www\.)?/, '')
    .replace(/^www\./, '')
    .replace(/\/$/, '')
}

function prevSlide(i) {
    const p = projects[i]
    p.currentIndex = (p.currentIndex - 1 + p.images.length) % p.images.length
}

function nextSlide(i) {
    const p = projects[i]
    p.currentIndex = (p.currentIndex + 1) % p.images.length
}

function goToSlide(i, idx) {
    projects[i].currentIndex = idx
}

function onTouchStart(event, i) {
    projects[i].touchStartX = event.touches[0].clientX
}

function onTouchMove(event, i) {
    projects[i].touchEndX = event.touches[0].clientX
}

function onTouchEnd(event, i) {
    const p = projects[i]
    const deltaX = p.touchStartX - p.touchEndX
    const threshold = 50

    if (deltaX > threshold) {
        nextSlide(i)
    } else if (deltaX < -threshold) {
        prevSlide(i)
    }
    p.touchStartX = 0
    p.touchEndX = 0
}
</script>

<style scoped>
.projects-section {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    margin-top: 10%;
}

.project {
    border-bottom: 2px #CCC solid;
}

.project-title {
    color: #8fbc83;
    font-size: 2rem;
    text-align: center;
    width: 100%;
}

.project-content {
    padding: 0px 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 1.5rem;
    margin: 2rem;
    background-color: #cccccc5f;
    width: 100vw;
    margin-top: 5%;
}

.columns {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    align-items: center;
    margin-bottom: 30px;
}

.project-info {
    max-width: 800px;
    flex: 1 1 50%;
    min-width: 300px;
}

.carousel-section {
    width: 100%;
    max-width: 800px;
    margin: 1rem auto 3rem auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.project-p {
    margin: 0.3rem 0;
}

.project-p strong {
    font-family: "Exo 2";
    font-weight: 700;
}
.description strong {
    font-family: "Exo 2";
    font-weight: 700;
}

.description {
    font-family: "Exo 2";
    font-weight: 400;
    background-color: #8fbc8351;
    padding: .2rem;
    margin-top: .7rem;
    margin-bottom: .7rem;
    white-space: pre-wrap;
}

.strong {
    font-family: "Exo 2";
    font-weight: bold;
    margin: 0.3rem 0;
    text-decoration: underline #8fbc83;
}

.link {
    color: #8fbc83;
    text-decoration: underline;
}

.project-gallery {
    flex: 1 1 40%;
    min-width: 280px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.slider-wrapper {
    position: relative;
    width: 100%;
    max-width: 800px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    aspect-ratio: 16 / 9;
}

.slider {
    flex: 0 1 auto;
    overflow: hidden;
    aspect-ratio: 16 / 9;
    position: relative;
    max-width: 100%;
}

.slider img.slide {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 2.5rem;
    background: transparent;
    border: none;
    color: #8fbc83;
    cursor: pointer;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    user-select: none;
    z-index: 2;
}

.arrow.left {
    left: -3rem;
}

.arrow.right {
    right: -3rem;
}

.dots {
    margin-top: 0.5rem;
    display: flex;
    gap: 0.5rem;
}

.dot {
    width: 10px;
    height: 10px;
    background: #ccc;
    border-radius: 50%;
    cursor: pointer;
}

.dot.active {
    background: #8fbc83;
}

.preview-image {
    width: 38em;
    cursor: pointer;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.2s;
}
.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.project-content.sit-nebo {
    --accent-color: #A6C8B1;
    --text-highlight: #B37C6C;
    --bg-description: #A6C8B166;
    --arrow-color: #3C3C3C;
}

.project-content.kupala {
    --accent-color: #C3A987;
    --text-highlight: #A6A6A6;
    --bg-description: #C3A98733;
    --arrow-color: #2C2C2C;
}

.project-content.altairika {
    --accent-color: #177fff;
    --text-highlight: #FF361B;
    --bg-description: rgb(255, 54, 27, 0.267);
    --arrow-color: #2C1F4C;
}

.project-title {
    color: var(--text-highlight);
}

.description {
    background-color: var(--bg-description);
}

.strong {
    text-decoration: underline var(--accent-color);
}

.link {
    color: var(--accent-color);
    text-decoration: underline;
}

.arrow {
    color: var(--arrow-color);
}

.dot.active {
    background: var(--accent-color);
}


@media (max-width: 768px) {
    .project-content {
        margin: 1rem 0;
        padding: 1rem;
        width: 100%;
        left: 0;
        transform: none;
    }

    .columns {
        flex-direction: column;
        align-items: stretch;
        gap: 1rem;
    }

    .project-info {
        max-width: 100%;
        min-width: 0;
        flex: 1 1 auto;
    }

    .project-gallery {
        max-width: 100%;
        min-width: 0;
    }

    .preview-image {
        width: 100%;
        max-width: 100%;
        height: auto;
    }

    .project-title {
        font-size: 1.5rem;
        padding: 0 1rem;
    }

    .slider-wrapper {
        flex-direction: row;
        gap: 0;
    }

    .arrow {
        font-size: 2rem;
        padding: 0.3rem 0.6rem;
    }

    .slider {
        width: 100%;
        max-width: 100%;
    }

    .arrow.left {
        left: .5rem;
    }

    .arrow.right {
        right: .5rem;
    }
}
</style>
