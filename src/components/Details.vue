<template>
    <section id="details" class="about-section">
        <div class="about-content fade-up">
            <h1>Обо мне</h1>
            <p>
                <strong class="strong">Unity-разработчик</strong>
                с более чем двухлетним опытом в разработке VR и 3D приложений. 
                Начинал как разработчик, затем перешёл на позицию тимлида. 
                В рамках этой роли координировал работу команды из 7 человек: 
                разбивал и планировал задачи, контролировал сроки и качество реализации, вёл задачи через Redmine.
            </p>
            <p>
                <strong class="strong">Регулярно</strong>
                проводил code review, администрировал репозитории в GitLab, поддерживал рабочие процессы. Взаимодействовал с заказчиками: помогал уточнять требования, формировал техническое видение и предлагал оптимальные решения.
                <br><strong class="strong">Отличаюсь</strong>
                системным мышлением, ответственным подходом и способностью доводить проект до стабильного, качественного релиза.
            </p>

            <h2>Навыки</h2>
            <ul class="skills-list decimal">
                <li><strong>Разработка на Unity и 3D-технологии</strong>
                    <p>
                        Настройка визуала и окружения (UI, URP/HDRP, Shader Graph, HLSL, Cinemachine, FMOD).
                        <br/>Построение архитектуры проекта (MVC, Zenject, Master-скрипты, Service Locator). 
                        <br/>Динамическая загрузка контента (Addressables, Asset Bundles). 
                        <br/>птимизация под различные платформы и отладка (Visual Studio, Unity Profiler).
                    </p>
                </li>
                <li><strong>Кроссплатформенная разработка и XR</strong>
                    <p>
                        Разработка под Oculus, OpenXR и 3D-платформы.
                    </p>
                </li>
                <li><strong>Сетевые технологии</strong>
                    <p>
                        Мультиплеер (Mirror), REST API, работа с данными (JSON, ScriptableObject).
                    </p>
                </li>
                <li><strong>Поддержка сетевой инфраструктуры</strong>
                    <p>
                        Настройка сервера, и развертывание Docker-контейнеров. 
                        <br/>Настройка Gitlab, Nextcloud и внедрение CI/CD для автоматической сборки и размещения Unity проектов.
                        <br/>Развертывание веб-сайтов (на одном из которых вы сейчас находитесь 😉).
                    </p>
                </li>
                <li><strong>Рабочие процессы</strong><p>Работа с Git (GitLab, Fork, Sourcetree). Управление задачами через Redmine.</p></li>
            </ul>

            <div class="education">
                <h2>Образование — Магистр (2027)</h2>
                <p>Уфимский университет науки и технологий | Институт информатики, математики и робототехники <br>
                    <strong>Математическое обеспечение и администрирование информационных систем<br>
                        (Математик-программист)</strong>
                </p>
            </div>

            <h2>Контакты — Глеб Панченко</h2>
            <ul class="contact-list">
                <li><strong>Email:</strong> <a href="mailto:work.pgv28@gmail.com">work.pgv28@gmail.com</a></li>
                <li><strong>Telegram:</strong> <a href="https://t.me/pgv_work" target="_blank">@pgv_work</a></li>
                <li><strong>Телефон:</strong> <a href="tel:+79191516697">+7 (919) 151-66-97</a></li>
                <li><strong>Город:</strong> Уфа</li>
                <li><strong>Гражданство:</strong> Россия (готов к переездам и командировкам)</li>
            </ul>
        </div>
    </section>
</template>


<style scoped>
.about-section {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 60px 20px;
    color: #222;
}

.about-content {
    max-width: 800px;
    margin: 0 auto;
    padding: 60px 20px;
}

.about-section h1 {
    font-size: 2rem;
    margin-bottom: 1rem;
}

.about-section h2 {
    margin-top: 1rem;
    margin-bottom: 1rem;
    border-top: 1px solid #ccc;
    padding-top: 1rem;
}

.about-section p {
    font-family: "Exo 2";
    font-weight: 600;
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: .5rem;
}

.strong {
    margin: 0.3rem 0;
    color: #8fbc83;
}

.skills-list {
    list-style: decimal;
    margin: 1rem;
}
.contact-list {
    list-style: none;
    padding: 0;
    margin: 1rem 0;
}

.skills-list li,
.contact-list li {
    margin-bottom: 0.5rem;
    font-family: "Exo 2";
    font-weight: 600;
}

.contact-list a {
    font-family: "Exo 2";
    font-weight: 600;
    color: #8fbc83;
    text-decoration: underline;
}
</style>