<template>
    <section id="projects" class="projects-section fade-up">
        <h2>Игровые проекты</h2>

        <div v-for="(project, index) in projects" :key="index" class="project">
            <h3>
                {{ project.title }}
            </h3>
            <p class="description">
                <strong>Описание: </strong>{{ project.description }}
            </p>
            <p class="strong"><strong>Роль:</strong> {{ project.role }}</p>
            <p class="strong"><strong>Технологии:</strong> {{ project.technologies }}</p>
            <ul>
                <li v-for="(item, i) in project.tasks" :key="i">{{ item }}</li>
            </ul>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

const projects = [
    {
        title: 'Полётный тренажёр',
        description: "VR-тренажёр для управления беспилотным летательным аппаратом. Проект включает мультиплеер, генерацию уровней, квестовую систему, AI, а также сетевую передачу данных.Особое внимание уделено кастомной графике, реалистичному звуку и кинематографичному опыту.",
        role: 'Team Lead (7 человек)',
        technologies: 'Mirror, Asset Bundles, Shader Graph, WebSockets, HDRP',
        tasks: [
            'Интеграция мультиплеера на Mirror',
            'Управление БПЛА с джойстика (Rewired)',
            'AI, генерация уровней, квестовая система',
            'Кастомные шейдеры, Cinemachine, FMOD',
            'Сохранения, WebSocket обмен с внешними устройствами'
        ]
    },
    {
        title: 'Конструктор ванных комнат',
        description: "Интерактивный конструктор, позволяющий пользователям проектировать ванные комнаты в 3D: размещать объекты, задавать параметры и сохранять конфигурации. Архитектура построена на Zenject и MVC. Использовались Addressables для оптимизации загрузки моделей.Интегрирован клиент- серверный обмен, авторизация и обновление токенов.",
        role: 'Team Lead (4 человека)',
        technologies: 'Zenject, MVC, Addressables, REST API',
        tasks: [
            'Интерактивный 3D-конструктор с сохранением конфигураций',
            'Загрузка моделей через Addressables',
            'UI Controller, Event Aggregator, Scene Loader',
            'Авторизация и обновление токенов'
        ]
    },
    {
        title: 'VR кинотеатр',
        description: 'Разработка полноценного VR-приложения для просмотра видеоконтента. Приложение поддерживает работу с медиатекой, оффлайн- доступ к видео и защищённое хранение данных.',
        role: 'Unity-разработчик (1 человек)',
        technologies: 'AVPro, REST API, Swagger, JSON, URP',
        tasks: [
            'Проигрывание видео в VR через AVPro',
            'Авторизация, сбор статистики, медиатека',
            'Оффлайн-доступ с шифрованием видеофайлов',
            'Оптимизация под VR с Unity Profiler'
        ]
    }
]
</script>

<style scoped>
.projects-section {
    padding: 80px 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.projects-section h2 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 2rem;
}

.project {
    box-shadow: 0 6px 8px rgba(0, 0, 0, 0.8);    
    width: 100%;
    max-width: 600px;
    margin-bottom: 3rem;
    background: #fff;
    padding: 2rem;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    position: relative;
}

.project h3 {
    color: #8fbc83;
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.description {
    font-family: "Exo 2";
    font-weight: 600;
    background-color: #8fbc8351;
    padding: .2rem;
    margin-bottom: 1rem;
}

.strong {
    margin: 0.3rem 0;
    text-decoration: underline #8fbc83;
}

.project ul {
    margin-top: 0.8rem;
    padding-left: 1.2rem;
    list-style-type: square;
}

.project ul li {
    margin-bottom: 0.5rem;
}
</style>
