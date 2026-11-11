<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Special Message For You - 11/11</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0d0d0d;
            background-image: radial-gradient(circle, #2d1524 0%, #0d0d0d 100%);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        /* Floating background hearts */
        .heart-bg {
            position: absolute;
            color: rgba(255, 77, 109, 0.2);
            font-size: 20px;
            animation: floatUp 6s linear infinite;
            z-index: 1;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(100vh) scale(0.5);
                opacity: 0;
            }
            50% {
                opacity: 0.8;
            }
            100% {
                transform: translateY(-10vh) scale(1.2);
                opacity: 0;
            }
        }

        .container {
            position: relative;
            z-index: 10;
            width: 100%;
            max-width: 400px;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Envelope Styles */
        .envelope-wrapper {
            cursor: pointer;
            transition: transform 0.5s ease;
            text-align: center;
        }

        .envelope-wrapper:hover {
            transform: scale(1.05);
        }

        .envelope {
            position: relative;
            width: 300px;
            height: 200px;
            background: linear-gradient(135deg, #f3c6df, #e295bc);
            border-radius: 0 0 10px 10px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }

        .envelope::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            border-left: 150px solid transparent;
            border-right: 150px solid transparent;
            border-top: 110px solid #cf7aab;
            transform-origin: top;
            transition: transform 0.4s ease 0.4s;
            z-index: 5;
        }

        /* Wax Seal */
        .seal {
            position: absolute;
            top: 75px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 50px;
            background: #b7094c;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 24px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.3);
            z-index: 6;
            transition: transform 0.3s ease;
        }

        .envelope-wrapper:hover .seal {
            transform: translateX(-50%) scale(1.1);
        }

        .envelope-text {
            margin-top: 25px;
            color: #ff4d6d;
            font-size: 1.2rem;
            font-weight: bold;
            letter-spacing: 1px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }

        /* Letter Modal / Card */
        .letter {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0);
            width: 90%;
            max-width: 360px;
            max-height: 80vh; /* التحكم في أقصى ارتفاع */
            background: #fff0f3;
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.4);
            z-index: 20;
            text-align: center;
            transition: transform 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            opacity: 0;
            pointer-events: none;
            overflow-y: auto; /* تفعيل السكرول الداخلي */
            -webkit-overflow-scrolling: touch;
        }

        .letter.active {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
            pointer-events: auto;
        }

        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid #ff4d6d;
            margin-bottom: 15px;
            box-shadow: 0 5px 15px rgba(255, 77, 109, 0.3);
        }

        .letter h2 {
            color: #b7094c;
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        .letter p {
            color: #590d22;
            font-size: 0.95rem;
            line-height: 1.6;
            margin-bottom: 20px;
            text-align: left; /* تنسيق النص بشكل أفضل للقراءة */
        }

        .audio-player {
            margin-top: 15px;
            width: 100%;
        }

        .close-btn {
            background-color: #ff4d6d;
            color: white;
            border: none;
            padding: 8px 20px;
            border-radius: 20px;
            font-size: 0.9rem;
            cursor: pointer;
            margin-top: 10px;
            transition: background 0.3s;
        }

        .close-btn:hover {
            background-color: #b7094c;
        }

        /* Opening Animation Classes */
        .envelope.open::before {
            transform: rotateX(180deg);
            z-index: 1;
        }
    </style>
</head>
<body>

    <!-- Background Floating Hearts -->
    <script>
        for (let i = 0; i < 20; i++) {
            let heart = document.createElement('div');
            heart.classList.add('heart-bg');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
            heart.style.animationDelay = (Math.random() * 5) + 's';
            document.body.appendChild(heart);
        }
    </script>

    <div class="container">
        <!-- Envelope Section -->
        <div class="envelope-wrapper" onclick="openEnvelope()">
            <div class="envelope" id="env">
                <div class="seal">❤️</div>
            </div>
            <div class="envelope-text">open me! 💌</div>
        </div>
    </div>

    <!-- Letter Content Modal -->
    <div class="letter" id="letterCard">
        <!-- ضع هنا اسم الصورة الخاصة بك -->
        <img src="7CD630FE-9E29-4BE5-A79C-0998FA00F116.jpeg" alt="Her Photo" class="profile-img">
        <h2>Happy 11/11 ❤️</h2>
        <p>
            "From the very first moment our paths crossed, my entire world shifted on its axis, and every single day since then has felt like a breathtaking journey I never want to end. You are the absolute light in my darkest days, the quiet peace in my busiest moments, and the reason behind every genuine smile that crosses my face. All of the numbers, dates, and hours of the day fade into absolute insignificance compared to the depth of what I feel for you. You are my today, my tomorrow, and every single beautiful dream I hold in my heart. No matter where life takes us or how fast the world moves around us, my heart will always recognize yours as its only true home. Thank you for being the most incredible, gorgeous, and magical part of my life, and for making every ordinary moment feel extraordinary just by being you."
       
            بحبك جنه ❤️
        </p>
        
        <!-- مشغل الصوت مضبوط على الأغنية الخاصة بك والبدء من الثانية 30 -->
        <audio id="loveSong" class="audio-player" controls loop>
            <source src="04.Kelma.mp3" type="audio/mpeg">
            Your browser does not support the audio element.
        </audio>

        <br>
        <button class="close-btn" onclick="closeEnvelope(event)">Close</button>
    </div>

    <script>
        function openEnvelope() {
            const env = document.getElementById('env');
            const letterCard = document.getElementById('letterCard');
            const song = document.getElementById('loveSong');

            env.classList.add('open');

            setTimeout(() => {
                letterCard.classList.add('active');
                song.currentTime = 30; // الأغنية تبدأ من الثانية 30
                song.play().catch(error => {
                    console.log("Autoplay prevented, user interaction required.");
                });
            }, 500);
        }

        function closeEnvelope(event) {
            event.stopPropagation();
            const env = document.getElementById('env');
            const letterCard = document.getElementById('letterCard');
            const song = document.getElementById('loveSong');

            letterCard.classList.remove('active');
            song.pause();
            song.currentTime = 0;

            setTimeout(() => {
                env.classList.remove('open');
            }, 300);
        }
    </script>
</body>
</html>

