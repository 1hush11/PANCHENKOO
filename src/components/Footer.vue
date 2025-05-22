<template>
    <footer class="site-footer">
        <div class="footer-content fade-up">
            <p>
                <a href="mailto:work.pgv28@gmail.com">work.pgv28@gmail.com</a> |
                <a href="https://t.me/pgv_work" target="_blank">Telegram</a> |
                <span class="mobile-break"><a href="/resume.pdf" download="Gleb_Panchenko_Resume.pdf">Скачать
                        резюме</a></span>
            </p>
            <p>
                <a class="none-decoration" href="#about">Знакомство</a> |
                <a class="none-decoration" href="#projects">Игровые проекты</a> |
                <a class="none-decoration" href="#details">Обо мне</a> |
                <a class="none-decoration" href="#hero">Наверх
                    <svg class="arrow-up" x="0px" y="0px" width="38.417px" height="18.592px" viewBox="0 0 38.417 18.592"
                        style="enable-background:new 0 0 38.417 18.592; fill: #8fbc83;">
                        <g>
                            <path
                                d="M19.208,18.592c-0.241,0-0.483-0.087-0.673-0.261L0.327,1.74c-0.408-0.372-0.438-1.004-0.066-1.413c0.372-0.409,1.004-0.439,1.413-0.066L19.208,16.24L36.743,0.261c0.411-0.372,1.042-0.342,1.413,0.066c0.372,0.408,0.343,1.041-0.065,1.413L19.881,18.332C19.691,18.505,19.449,18.592,19.208,18.592z" />
                        </g>
                    </svg>
                </a>
            </p>
            <p style="padding-top: 2rem;">© 2025 Глеб Панченко — Unity Developer</p>
        </div>
    </footer>
</template>  


<style scoped>
.site-footer {
    background-color: rgba(17, 17, 17, 0.95);
    color: #ccc;
    text-align: center;
    padding: 2rem 1rem;
    font-size: 0.9rem;
    font-family: "Exo 2", sans-serif;
}

.site-footer a {
    color: #8fbc83;
    text-decoration: underline;
    margin: 0 0.5rem;
}

.site-footer a:hover {
    color: #ffffff;
}

.site-footer .none-decoration {
    align-items: center;
    text-decoration: none;
}

.arrow-up {
    color: #8fbc83;
    transform: rotate(180deg);
    vertical-align: middle;
    margin-left: 0.3rem;
    width: 1rem;
    height: auto;
    top: -50px;
} 

@media (max-width: 600px) {
    .mobile-break {
        display: block;
        margin-top: 0.5rem;
    }
}
</style>
