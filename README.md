<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Bhime mal 💖</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #ffe6f2;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Arial', cursive;
        }

        .card-container {
            position: relative;
            width: 400px;
            height: 600px;
        }

        .page {
            position: absolute;
            width: 100%;
            height: 100%;
            background: #fff;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(255, 0, 102, 0.2);
            padding: 30px;
            transition: transform 0.8s;
            transform-style: preserve-3d;
            backface-visibility: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            overflow: hidden;
        }

        .page:not(.active) {
            transform: rotateY(180deg);
        }

        .cover {
            background: linear-gradient(45deg, #ff007f, #ff1493);
            color: white;
            text-align: center;
        }

        .heart {
            position: absolute;
            font-size: 100px;
            color: #ff0066;
            animation: pulse 1.2s infinite;
            margin-top: 100px;
        }

        h1 {
            font-size: 2.5em;
            margin-top: 200px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .page2 {
            background: #fff0f6;
        }

        .message {
            font-size: 1.2em;
            line-height: 1.6;
            text-align: center;
            margin-top: 50px;
            animation: fadeIn 2s;
        }

        .page3 {
            background: #ffeff7;
        }

        .hearts-container {
            position: relative;
            margin-top: 100px;
        }

        .beating-heart {
            font-size: 80px;
            color: #ff0066;
            animation: beat 1s infinite;
        }

        .page4 {
            background: #ffe6f2;
        }

        .photo-frame {
            width: 200px;
            height: 200px;
            border: 5px solid #ff0066;
            border-radius: 50%;
            margin-top: 50px;
            overflow: hidden;
        }

        .photo-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .navigation {
            position: absolute;
            bottom: 20px;
            display: flex;
            gap: 20px;
        }

        button {
            padding: 10px 20px;
            background: #ff0066;
            color: white;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            transition: transform 0.3s;
        }

        button:hover {
            transform: scale(1.1);
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        @keyframes beat {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="card-container">
        <!-- Page 1 - Cover -->
        <div class="page cover active">
            <div class="heart">💖</div>
            <h1>Happy Valentine's<br>Bhimey mal</h1>
            <div class="navigation">
                <button onclick="nextPage()">Open</button>
            </div>
        </div>

        <!-- Page 2 -->
        <div class="page page2">
            <p class="message">
                To My Dearest Mal,<br><br>
                You make my world brighter every day. 
                Your smile is my favorite sight, your laugh my favorite sound. 
                I cherish every moment we share together.
            </p>
            <div class="navigation">
                <button onclick="prevPage()">Back</button>
                <button onclick="nextPage()">Next</button>
            </div>
        </div>

        <!-- Page 3 -->
        <div class="page page3">
            <div class="hearts-container">
                <div class="beating-heart">💝</div>
            </div>
            <p class="message" style="margin-top: 30px;">
                You're the missing piece I've been searching for. 
                Thank you for being my everything. 
                My love for you grows stronger every day.
            </p>
            <div class="navigation">
                <button onclick="prevPage()">Back</button>
                <button onclick="nextPage()">Next</button>
            </div>
        </div>

        <!-- Page 4 -->
        <div class="page page4">
            <div class="photo-frame">
                <!-- Add your photo here -->
                <img src="your-photo.jpg" alt="Our Photo">
            </div>
            <p class="message" style="margin-top: 30px;">
                Forever Yours,<br>
                Milan<br><br>
                💖 Will you be my Valentine? 💖
            </p>
            <div class="navigation">
                <button onclick="prevPage()">Back</button>
                <button onclick="resetCard()">Start Over</button>
            </div>
        </div>
    </div>

    <script>
        let currentPage = 1;
        const pages = document.querySelectorAll('.page');

        function nextPage() {
            if (currentPage < pages.length) {
                pages[currentPage - 1].classList.remove('active');
                pages[currentPage].classList.add('active');
                currentPage++;
            }
        }

        function prevPage() {
            if (currentPage > 1) {
                pages[currentPage - 1].classList.remove('active');
                pages[currentPage - 2].classList.add('active');
                currentPage--;
            }
        }

        function resetCard() {
            currentPage = 1;
            pages.forEach(page => page.classList.remove('active'));
            pages[0].classList.add('active');
        }
    </script>
</body>
</html>
