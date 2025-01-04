
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to Aryan's Website</title>
    <style>
        body {
            margin: 0;
            font-family: "Courier New", Courier, monospace;
            background: black;
            color: white;
            overflow: hidden;
        }
        #welcomePage {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            background: linear-gradient(45deg, black, darkred);
            animation: pulse 2s infinite;
        }
        #welcomePage h1 {
            font-size: 36px;
            color: white;
            text-shadow: 0 0 10px red, 0 0 20px red;
            margin-bottom: 20px;
        }
        #enterButton {
            padding: 15px 30px;
            font-size: 20px;
            color: white;
            background: red;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            box-shadow: 0 0 10px red, 0 0 20px red;
            animation: flicker 1.5s infinite;
        }
        #enterButton:hover {
            background: darkred;
            box-shadow: 0 0 15px white, 0 0 30px white;
        }
        @keyframes pulse {
            0%, 100% {
                background: linear-gradient(45deg, black, darkred);
            }
            50% {
                background: linear-gradient(45deg, black, red);
            }
        }
        @keyframes flicker {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }
        #prankPage {
            display: none;
        }
    </style>
</head>
<body>
    <!-- Welcome Page -->
    <div id="welcomePage">
        <h1>Welcome to Aryan's Website</h1>
        <button id="enterButton">Press Here</button>
    </div>

    <!-- Prank Page -->
    <div id="prankPage">
        <div class="terminal" id="terminal">
            <div class="hacker-text" id="hackerText">Initializing system...</div>
        </div>
        <audio id="horrorAudio" src="https://freesound.org/data/previews/415/415764_5121236-lq.mp3"></audio>
    </div>

    <script>
        const welcomePage = document.getElementById("welcomePage");
        const prankPage = document.getElementById("prankPage");
        const enterButton = document.getElementById("enterButton");
        const hackerText = document.getElementById("hackerText");
        const horrorAudio = document.getElementById("horrorAudio");

        // Messages for the "hacked" prank
        const messages = [
            "Accessing system files...",
            "Attempting login...",
            "Password accepted.",
            "Downloading sensitive data...",
            "WARNING: Unauthorized access detected!",
            "Tracing your IP address...",
            "Location: [ultratech . cement plnat rawan grasim vihar,.. chattisgarh, INDIA]",
            "ALL YOUR FILES HAVE BEEN COMPROMISED.",
            "Deploying ransomware in 3... 2... 1..."
        ];

        let index = 0;

        // Switch to the prank page
        enterButton.addEventListener("click", () => {
            welcomePage.style.display = "none";
            prankPage.style.display = "block";
            horrorAudio.play();
            horrorAudio.loop = true;
            typeNextMessage();
        });

        // Display messages one by one
        function typeNextMessage() {
            if (index < messages.length) {
                hackerText.innerText = messages[index];
                index++;
                setTimeout(typeNextMessage, 3000);
            } else {
                endPrank();
            }
        }

        // Final prank message
        function endPrank() {
            hackerText.innerHTML = '<span style="color: red; font-size: 24px; font-weight: bold;">YOUR SYSTEM IS HACKED!</span>';
            document.body.style.background = "red";
        }
    </script>
</body>
