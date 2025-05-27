<template>
<section id="about" class="about-section">
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
</script>

<style scoped>

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
