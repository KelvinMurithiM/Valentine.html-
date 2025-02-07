<audio id="backgroundMusic" loop></audio>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Day Surprise</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ffebee;
            text-align: center;
            padding: 50px;
            overflow: hidden;
        }
        h1 {
            color: #d32f2f;
            font-size: 3rem;
            animation: float 3s ease-in-out infinite;
        }
        p {
            font-size: 1.5rem;
            color: #555;
        }
        .password-page, .question-page, .flowers-page {
            display: none;
        }
        .password-page.active, .question-page.active, .flowers-page.active {
            display: block;
        }
        .password-input {
            margin-top: 20px;
        }
        .password-input input {
            padding: 10px;
            font-size: 1rem;
            border: 2px solid #d32f2f;
            border-radius: 5px;
        }
        .password-input button {
            padding: 10px 20px;
            font-size: 1rem;
            background-color: #d32f2f;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .cat-hearts {
            margin-top: 30px;
        }
        .cat-hearts img {
            width: 100px;
            margin: 10px;
            animation: float 4s ease-in-out infinite;
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            font-size: 1.2rem;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: transform 0.2s;
        }
        #yesButton {
            background-color: #4CAF50;
            color: white;
        }
        #noButton {
            background-color: #f44336;
            color: white;
        }
        #noButton:hover {
            transform: translate(calc(100px - var(--random-x)), calc(100px - var(--random-y)));
        }
        .hidden {
            display: none;
        }
        #response {
            margin-top: 30px;
            font-size: 2rem;
            color: #d32f2f;
            animation: bounce 2s infinite;
        }
        .flowers-page img {
            width: 150px;
            margin: 20px;
            animation: float 6s ease-in-out infinite;
        }
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }
    </style>
</head>
<body>
    <!-- Password Page -->
    <div class="password-page active">
        <h1>Welcome to My Valentine's Surprise!</h1>
        <p>Enter the password to proceed:</p>
        <div class="password-input">
            <input type="text" id="password" placeholder="Enter password">
            <button onclick="checkPassword()">Submit</button>
        </div>
        <div class="cat-hearts">
            <img src="https://media1.tenor.com/m/pRYo6fmexbgAAAAC/peach-goma.gif" alt="Cute Cat" style="width: 300px;">
        </div>
        </div>

        <!-- Question Page -->
        <div class="question-page">
        <h1>Will You Be My Valentine?</h1>
        <img src="file:///C:/Users/Hp/DOWNLOADS/catflower.jpg" alt="Cute Panda" style="width: 300px">
        <div class="buttons">
            <button id="yesButton">Yes!</button>
            <button id="noButton">No</button>
        </div>
        <div id="response" class="hidden">
            💖 Yay! You just made me the happiest person ever! 💖
        </div>
    </div>

    <!-- Flowers Page -->
    <div class="flowers-page">
        <h1>Thank You for Saying Yes!</h1>
        <p>Here are some beautiful flowers for you:</p>
        <div>
            <img src="https://media.tenor.com/p96XUHeS4q8AAAAi/peach-and-goma-goma.gif" alt="Flowers" style="width: 400px;">
        </div>
    </div>

    <!-- Audio -->
    <audio id="backgroundMusic" loop>
        <source src="file:///C:/Users/Hp/DOWNLOADS/beabadoobee%20-%20Glue%20Song%20(Official%20Music%20Video).mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <script>
        // Password Check
        function checkPassword() {
            const password = document.getElementById('password').value;
            if (password === '2005') {
                document.querySelector('.password-page').classList.remove('active');
                document.querySelector('.question-page').classList.add('active');
                document.getElementById('backgroundMusic').play();
            } else {
                alert('Incorrect password! Try again.');
            }
        }

        // Question Page Logic
        const yesButton = document.getElementById('yesButton');
        const noButton = document.getElementById('noButton');
        const response = document.getElementById('response');

        yesButton.addEventListener('click', () => {
            document.querySelector('.question-page').classList.remove('active');
            document.querySelector('.flowers-page').classList.add('active');
        });

        noButton.addEventListener('mouseover', () => {
            const randomX = Math.random() * 200 - 100;
            const randomY = Math.random() * 200 - 100;
            noButton.style.setProperty('--random-x', randomX + 'px');
            noButton.style.setProperty('--random-y', randomY + 'px');
            response.textContent = "Pretty pleeease? 🥺";
            response.classList.remove('hidden');
            yesButton.style.fontSize = (parseInt(window.getComputedStyle(yesButton).fontSize) + 2) + 'px';
        });
    </script>
</body>
</html>
