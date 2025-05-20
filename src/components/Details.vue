<template>
    <section id="details" class="about-section">
        <div class="about-content fade-up">
            <h1>О себе</h1>
            <p>
                <strong class="strong">Unity-разработчик</strong>
                с более чем 2 годами опыта в создании интерактивных приложений, преимущественно в сфере VR и
                3D-конструкторов. Руководил командами до 7 человек, принимал участие в архитектурном проектировании,
                разработке систем с нуля и оптимизации под разные платформы (PC, VR).
            </p>
            <p>
                <strong class="strong">Уверенно работаю</strong>
                с современным стеком Unity: от Zenject и Addressables до мультиплеера на Mirror и интеграции с внешними
                API.
                Регулярно провожу code review, пишу техническую документацию и участвую в подборе разработчиков.
                <br><strong class="strong">Сильные стороны</strong> — системное мышление, умение принимать архитектурные
                решения и доводить проект до готового продукта.
            </p>

            <div class="education">
                <h2>Образование — Магистр (2027)</h2>
                <p>Уфимский университет науки и технологий | Институт информатики, математики и робототехники <br>
                    <strong>Математическое обеспечение и администрирование информационных систем<br>
                        (Математик-программист)</strong>
                </p>
            </div>

            <h2>Навыки</h2>
            <ul class="skills-list decimal">
                <li>Unity (URP, HDRP, Shader Graph, Addressables)</li>
                <li>VR (Oculus, OpenXR), 3D UI, Cinemachine, FMOD</li>
                <li>Game architecture (MVC, Zenject, ScriptableObjects)</li>
                <li>Mirror, WebSockets, REST API, JSON, AVPro</li>
                <li>Git (CLI, Sourcetree), Agile, Code Review</li>
                <li>Документирование, управление задачами, тимлидство</li>
            </ul>

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
    font-size: xx-large;
    margin-bottom: 1rem;
}

.about-section h2 {
    margin-top: 2rem;
    margin-bottom: 1rem;
    border-top: 1px solid #ccc;
    padding-top: 1rem;
}

.about-section p {
    font-family: "Exo 2";
    font-weight: 600;
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: 1rem;
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