<template>
    <section id="about" class="about-section">
        <div class="about-content">
            <div class="state">
                <img src="@/assets/avatar.jpg" alt="Глеб Панченко" class="avatar" />
                <div class="text">
                    <h2>Панченко Глеб</h2>
                    <p class="experience">Опыт разработки на Unity — 2+ года</p>
                </div>
            </div>
            <p class="intro">
                Привет! Вы находитесь на странице моего портфолио. Здесь я демонстрирую результаты своего опыта
                разработки игр и приложений с использованием C#, Unity и VR-технологий.
            </p>
        </div>

        <div class="tech-section">
            <h3>Технологии, которыми я владею</h3>
            <p>Unity, C#, VR (Oculus, OpenXR), Mirror, Shader Graph, <br>REST API, FMOD, Zenject, MVC, Git, Addressables</p>
        </div>
    </section>
</template>

<script setup>
</script>

<style scoped>
.about-section {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: #8fbc831a;
    padding: 60px 20px;
    color: #222;
}

.about-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 60px;
}

.state {
    display: flex;
    align-items: center;
    justify-content: start;
    gap: 1rem;
    margin-bottom: 1rem;
}

.avatar {
    width: 20vh;
    height: 20vh;
    border-radius: 100%;
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
