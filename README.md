<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">

<meta name="viewport"
      content="width=device-width,
               initial-scale=1.0,
               maximum-scale=1.0,
               user-scalable=no">

<meta name="theme-color" content="#ff4f81">

<title>Для тебя ❤️</title>

<style>

* {
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
}

html,
body {
    width: 100%;
    height: 100%;
    margin: 0;
    overflow: hidden;
}

body {
    font-family:
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        Roboto,
        Arial,
        sans-serif;

    background:
        linear-gradient(
            135deg,
            #fff1f5,
            #f4e8ff
        );

    color: #302631;
}


/* =========================
   ЭКРАНЫ
========================= */

.screen {

    position: fixed;

    inset: 0;

    display: flex;

    align-items: center;

    justify-content: center;

    padding: 20px;

    opacity: 0;

    visibility: hidden;

    pointer-events: none;

    transform: translateY(20px);

    transition:
        opacity .4s ease,
        transform .4s ease,
        visibility .4s;
}


.screen.active {

    opacity: 1;

    visibility: visible;

    pointer-events: auto;

    transform: translateY(0);
}


/* =========================
   КАРТОЧКА
========================= */

.card {

    width: 100%;

    max-width: 430px;

    padding: 32px 22px 28px;

    text-align: center;

    background: rgba(255,255,255,.92);

    border-radius: 30px;

    box-shadow:
        0 20px 60px
        rgba(70,30,60,.15);

    backdrop-filter: blur(15px);
}


/* =========================
   ТЕКСТ
========================= */

.emoji {

    font-size: 58px;

    line-height: 1;

    margin-bottom: 16px;

    animation: floating 2.5s ease-in-out infinite;
}


h1 {

    font-size:
        clamp(28px, 8vw, 40px);

    line-height: 1.1;

    margin:
        0 0 14px;
}


p {

    font-size: 17px;

    line-height: 1.45;

    color: #6d5d69;

    margin:
        0 0 25px;
}


/* =========================
   КНОПКИ ПЕРВОГО ЭКРАНА
========================= */

.button-area {

    position: relative;

    width: 100%;

    height: 170px;
}


button {

    font-family: inherit;

    border: none;

    cursor: pointer;

    touch-action: manipulation;

    -webkit-user-select: none;

    user-select: none;
}


/* ДА */

.yes-button {

    position: absolute;

    left: 50%;

    top: 5px;

    transform: translateX(-50%);

    padding:
        15px 34px;

    border-radius: 999px;

    background: #ff4f81;

    color: white;

    font-size: 18px;

    font-weight: 700;

    box-shadow:
        0 10px 25px
        rgba(255,79,129,.3);
}


.yes-button:active {

    transform:
        translateX(-50%)
        scale(.95);
}


/* НЕТ */

.no-button {

    position: absolute;

    left: 50%;

    top: 90px;

    padding:
        13px 25px;

    border-radius: 999px;

    background: #eee8ed;

    color: #756a74;

    font-size: 17px;

    font-weight: 700;

    white-space: nowrap;

    transition:
        left .15s ease,
        top .15s ease;
}


/* =========================
   ВАРИАНТЫ
========================= */

.choices {

    display: grid;

    gap: 12px;
}


.choice-button {

    width: 100%;

    padding:
        16px 18px;

    border-radius: 18px;

    border:
        2px solid #f0dce6;

    background: white;

    color: #403642;

    text-align: left;

    font-size: 17px;

    font-weight: 600;

    box-shadow:
        0 6px 16px
        rgba(76,41,64,.06);

    transition:
        transform .15s,
        background .15s,
        border-color .15s;
}


.choice-button:active {

    transform: scale(.97);
}


.choice-button.selected {

    border-color: #ff4f81;

    background: #fff0f5;
}


.hint {

    margin-top: 17px;

    font-size: 14px;

    color: #978893;
}


/* =========================
   ФИНАЛ
========================= */

.result {

    font-size: 25px;

    font-weight: 800;

    color: #ff4f81;

    margin:
        14px 0 24px;
}


.restart-button {

    padding:
        13px 25px;

    border-radius: 999px;

    background: #302631;

    color: white;

    font-size: 16px;

    font-weight: 700;
}


/* =========================
   СЕРДЕЧКИ
========================= */

.heart {

    position: fixed;

    z-index: 100;

    pointer-events: none;

    font-size: 21px;

    animation:
        heart-animation 1.5s
        ease-out forwards;
}


/* =========================
   АНИМАЦИИ
========================= */

@keyframes floating {

    0%,100% {
        transform: translateY(0);
    }

    50% {
        transform: translateY(-7px);
    }
}


@keyframes heart-animation {

    0% {

        opacity: 1;

        transform:
            translateY(0)
            scale(1);
    }

    100% {

        opacity: 0;

        transform:
            translateY(-120px)
            scale(1.6)
            rotate(15deg);
    }
}


.shake {

    animation:
        shake-animation .25s ease;
}


@keyframes shake-animation {

    0%,100% {
        transform: translateX(0);
    }

    25% {
        transform: translateX(-5px);
    }

    75% {
        transform: translateX(5px);
    }
}

</style>
</head>


<body>


<!-- =====================================================
     ЭКРАН 1
===================================================== -->

<section
    class="screen active"
    id="screen1"
>

    <div
        class="card"
        id="firstCard"
    >

        <div class="emoji">
            ❤️
        </div>

        <h1 id="question">
        </h1>

        <p>
            Подумай хорошенько...
            хотя правильный ответ очевиден 😏
        </p>


        <div
            class="button-area"
            id="buttonArea"
        >

            <button
                class="yes-button"
                id="yesButton"
            >
                Да ❤️
            </button>


            <button
                class="no-button"
                id="noButton"
            >
                Нет 😏
            </button>

        </div>

    </div>

</section>



<!-- =====================================================
     ЭКРАН 2
===================================================== -->

<section
    class="screen"
    id="screen2"
>

    <div class="card">

        <div class="emoji">
            🥰
        </div>

        <h1>
            Отлично!
        </h1>

        <p>
            А теперь выбери,
            что будем делать:
        </p>


        <div
            class="choices"
            id="choices"
        >
        </div>


        <div class="hint">
            Выбери один вариант
        </div>

    </div>

</section>



<!-- =====================================================
     ЭКРАН 3
===================================================== -->

<section
    class="screen"
    id="screen3"
>

    <div class="card">

        <div class="emoji">
            🎉
        </div>

        <h1>
            Тогда решено! ❤️
        </h1>

        <p>
            Сегодня нас ждёт:
        </p>


        <div
            class="result"
            id="result"
        >
        </div>


        <p>
            Я уже всё придумал 😉
        </p>


        <button
            class="restart-button"
            id="restartButton"
        >
            Начать сначала
        </button>

    </div>

</section>



<script>

/* =====================================================
   НАСТРОЙКИ

   ВОТ ЗДЕСЬ ПОТОМ МОЖНО МЕНЯТЬ ТЕКСТЫ
===================================================== */

const settings = {

    question:
        "Пойдёшь со мной на свидание?",

    yesButton:
        "Да ❤️",

    noButton:
        "Нет 😏",

    choices: [

        "🍷 Ресторан",

        "🎬 Кино",

        "🌃 Прогулка",

        "🎁 Что-нибудь необычное"

    ]

};


/* =====================================================
   ЭЛЕМЕНТЫ
===================================================== */

const screen1 =
    document.getElementById("screen1");

const screen2 =
    document.getElementById("screen2");

const screen3 =
    document.getElementById("screen3");


const card =
    document.getElementById("firstCard");

const area =
    document.getElementById("buttonArea");


const yesButton =
    document.getElementById("yesButton");

const noButton =
    document.getElementById("noButton");


const choicesContainer =
    document.getElementById("choices");

const result =
    document.getElementById("result");


/* =====================================================
   ЗАПОЛНЯЕМ ТЕКСТ
===================================================== */

document.getElementById("question")
    .textContent =
    settings.question;


yesButton.textContent =
    settings.yesButton;


noButton.textContent =
    settings.noButton;



/* =====================================================
   ПЕРЕКЛЮЧЕНИЕ ЭКРАНОВ
===================================================== */

function showScreen(screen) {

    screen1.classList.remove("active");

    screen2.classList.remove("active");

    screen3.classList.remove("active");

    screen.classList.add("active");
}



/* =====================================================
   СЕРДЕЧКО
===================================================== */

function createHeart(x, y) {

    const heart =
        document.createElement("div");

    heart.className = "heart";

    const hearts = [
        "❤️",
        "💕",
        "💖",
        "💗"
    ];

    heart.textContent =
        hearts[
            Math.floor(
                Math.random() *
                hearts.length
            )
        ];

    heart.style.left =
        x + "px";

    heart.style.top =
        y + "px";

    document.body.appendChild(heart);

    setTimeout(() => {

        heart.remove();

    }, 1500);
}



/* =====================================================
   УБЕГАЮЩАЯ КНОПКА
===================================================== */

function moveNoButton(event) {

    if (event) {

        event.preventDefault();

    }


    const areaWidth =
        area.clientWidth;

    const areaHeight =
        area.clientHeight;


    const buttonWidth =
        noButton.offsetWidth;

    const buttonHeight =
        noButton.offsetHeight;


    const padding = 5;


    const maxLeft =
        Math.max(
            padding,
            areaWidth -
            buttonWidth -
            padding
        );


    const maxTop =
        Math.max(
            padding,
            areaHeight -
            buttonHeight -
            padding
        );


    const newLeft =
        padding +
        Math.random() *
        maxLeft;


    const newTop =
        padding +
        Math.random() *
        maxTop;


    noButton.style.left =
        newLeft + "px";


    noButton.style.top =
        newTop + "px";


    noButton.style.transform =
        "none";


    card.classList.remove("shake");

    void card.offsetWidth;

    card.classList.add("shake");


    createHeart(
        window.innerWidth / 2,
        window.innerHeight / 2
    );
}



/* =====================================================
   КОМПЬЮТЕР

   Убегает при наведении
===================================================== */

noButton.addEventListener(
    "mouseenter",
    moveNoButton
);



/* =====================================================
   ТЕЛЕФОН

   При попытке прикоснуться —
   кнопка убегает
===================================================== */

noButton.addEventListener(
    "pointerdown",
    function(event) {

        if (
            event.pointerType ===
            "touch"
        ) {

            moveNoButton(event);

        }

    }
);



/* =====================================================
   ЗАПАСНОЙ CLICK
===================================================== */

noButton.addEventListener(
    "click",
    function(event) {

        event.preventDefault();

        moveNoButton(event);

    }
);



/* =====================================================
   КНОПКА ДА
===================================================== */

yesButton.addEventListener(
    "click",
    function() {

        createHeart(
            window.innerWidth / 2,
            window.innerHeight / 2
        );


        setTimeout(
            function() {

                showScreen(screen2);

            },
            200
        );

    }
);



/* =====================================================
   ВАРИАНТЫ
===================================================== */

settings.choices.forEach(
    function(choiceText) {

        const button =
            document.createElement(
                "button"
            );


        button.className =
            "choice-button";


        button.textContent =
            choiceText;


        button.addEventListener(
            "click",
            function() {

                document
                    .querySelectorAll(
                        ".choice-button"
                    )
                    .forEach(
                        function(button) {

                            button.classList
                                .remove(
                                    "selected"
                                );

                        }
                    );


                button.classList.add(
                    "selected"
                );


                result.textContent =
                    choiceText;


                setTimeout(
                    function() {

                        showScreen(screen3);


                        for (
                            let i = 0;
                            i < 10;
                            i++
                        ) {

                            setTimeout(
                                function() {

                                    createHeart(
                                        Math.random() *
                                        window.innerWidth,

                                        window.innerHeight *
                                        (
                                            .45 +
                                            Math.random() *
                                            .3
                                        )
                                    );

                                },

                                i * 80
                            );

                        }

                    },

                    300
                );

            }
        );


        choicesContainer.appendChild(
            button
        );

    }
);



/* =====================================================
   НАЧАТЬ СНАЧАЛА
===================================================== */

document
    .getElementById("restartButton")
    .addEventListener(
        "click",
        function() {

            noButton.style.left =
                "50%";

            noButton.style.top =
                "90px";

            noButton.style.transform =
                "translateX(-50%)";


            document
                .querySelectorAll(
                    ".choice-button"
                )
                .forEach(
                    function(button) {

                        button.classList
                            .remove(
                                "selected"
                            );

                    }
                );


            showScreen(screen1);

        }
    );

</script>

</body>
</html>
