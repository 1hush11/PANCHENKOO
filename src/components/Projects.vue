<template>
    <section id="projects" class="projects-section fade-up">
        <div v-for="(project, index) in projects" :key="index" class="project">
            <div class="project-content">
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
                        <a class="link" :href="project.link" target="_blank">{{ project.link }}</a>
                    </p>
                    </div>
                    
                    <div class="project-gallery" v-if="project.images && project.images.length">
                        <img
                            :src="project.preview"
                            class="preview-image"
                            alt="preview"
                        />
                    </div>
                </div>

            </div>
            <div
                class="carousel-section"
                v-if="project.images.length > 1"
            >
                <div class="slider-wrapper">
                    <button class="arrow left" @click="prevSlide(index)"><</button>

                    <div class="slider">
                        <transition name="fade" mode="out-in">
                        <img
                            :src="project.images[project.currentIndex]"
                            :key="project.currentIndex"
                            class="slide"
                        />
                        </transition>
                    </div>

                    <button class="arrow right" @click="nextSlide(index)">></button>
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
import { reactive, ref } from 'vue'

const projects = reactive([
    {
        title: 'VR – кинотеатр',
        duration: '6 месяцев',
        description: "VR-приложение для просмотра видеоконтента в виртуальном пространстве. Поддерживаются режимы 180° и 360°, а также полноценное управление медиатекой. Реализован оффлайн-доступ к видеофайлам для использования без подключения к интернету. Данные пользователей и контент защищены с помощью системы шифрования. Приложение построено на клиент-серверной архитектуре с авторизацией и сбором статистики. Оптимизировано под VR-устройства, включая устаревшую платформу Oculus Go.",
        role: 'Unity-разработчик',
        technologies: 'URP, Figma, AVPro, REST API, JSON, Swagger, Unity Profiler',
        link: 'https://altairika.com/',
        preview: '/assets/Hall.jpg',
        images: [
            '/assets/image15.jpg',
            '/assets/image16.jpg',
            '/assets/image17.jpg',
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
        preview: '/assets/sit-preview.jpeg',
        images: [
            '/assets/image1.jpg',
            '/assets/image2.jpg',
            '/assets/image3.jpg',
            '/assets/image4.jpg',
            '/assets/image5.jpg',
            '/assets/image6.jpg',
            '/assets/image7.jpg',
        ],
        currentIndex: 0,
    },
    {
        title: 'Конструктор ванных комнат',
        duration: '5 месяцев',
        description: "Приложение для сотрудников торговых сетей, позволяющее проектировать ванные комнаты с учётом индивидуальных пожеланий клиента. Интерактивный конструктор обеспечивает удобное размещение объектов с возможностью задания размеров, материалов и цветовых решений. Готовые проекты автоматически сохраняются на сервере и доступны для дальнейшей модерации. Реализована генерация технической документации для производства и возможность отправки проекта с сопроводительной информацией на электронную почту клиента. Дополнительный функционал включает отображение размеров изделий и переключение режимов камеры для удобного обзора сцены.",
        role: 'Team Lead',
        technologies: 'HDRP, Figma, Zenject, MVC, Addressables, Event Aggregator, REST API, JSON, Swagger',
        link: 'https://kupalapro.ru/',
        preview: '/assets/kupala-preview.jpg',
        images: [
            '/assets/image8.png',
            '/assets/image9.png',
            '/assets/image10.png',
            '/assets/image11.png',
            '/assets/image12.png',
            '/assets/image13.png',
            '/assets/image14.png',
        ],
        currentIndex: 0,
    },
])

function prevSlide(projectIndex) {
    const project = projects[projectIndex]
    project.currentIndex =
    (project.currentIndex - 1 + project.images.length) % project.images.length
}

function nextSlide(projectIndex) {
    const project = projects[projectIndex]
    project.currentIndex = (project.currentIndex + 1) % project.images.length
}

function goToSlide(projectIndex, imageIndex) {
    projects[projectIndex].currentIndex = imageIndex
}
</script>

<style scoped>
.projects-section {
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
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
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 1.5rem;
    margin: 2rem;
}

.columns {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    align-items: flex-start;
}

.project-info {
    flex: 1 1 50%;
    min-width: 300px;
}

.carousel-section {
    width: 100%;
    max-width: 900px;
    margin: 1rem auto 3rem auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.project-p {
    margin: 0.3rem 0;
}

.description {
    font-family: "Exo 2";
    font-weight: 600;
    background-color: #8fbc8351;
    padding: .2rem;
    margin-top: .7rem;
    margin-bottom: .7rem;
}

.strong {
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
    max-width: 900px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
}

.slider {
    flex: 1;
    overflow: hidden;
    aspect-ratio: 16 / 9;
    position: relative;
}

.slider img.slide {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.arrow {
    font-family: 'Inter', sans-serif;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    color: #8fbc83;
    cursor: pointer;
    font-size: 2.5rem;
    background: transparent;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    z-index: 1;
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
    width: 100%;
    border-radius: 10px;
    cursor: pointer;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.3s;
}
.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>
