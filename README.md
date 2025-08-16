<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎉 Special Surprise</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #ff6b6b 100%);
            background-size: 200% 200%;
            animation: gradientShift 8s ease infinite;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow-x: hidden;
            position: relative;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .floating-shapes {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }

        .shape {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .shape:nth-child(1) { width: 80px; height: 80px; left: 10%; animation-delay: 0s; }
        .shape:nth-child(2) { width: 120px; height: 120px; left: 20%; animation-delay: 2s; }
        .shape:nth-child(3) { width: 60px; height: 60px; left: 80%; animation-delay: 4s; }
        .shape:nth-child(4) { width: 100px; height: 100px; left: 70%; animation-delay: 1s; }

        @keyframes float {
            0%, 100% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10%, 90% { opacity: 0.7; }
            50% { transform: translateY(-100px) rotate(180deg); }
        }

        .container {
            text-align: center;
            color: white;
            max-width: 500px;
            width: 90%;
            padding: 2rem;
            position: relative;
            z-index: 10;
        }

        .login-section {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(20px);
            border-radius: 25px;
            padding: 3rem 2.5rem;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            animation: fadeInUp 1.2s ease-out;
        }

        .surprise-section {
            display: none;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 {
            font-size: 2.8rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ffd700, #ff6b6b, #4ecdc4);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: textShimmer 3s ease-in-out infinite;
        }

        @keyframes textShimmer {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .subtitle {
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            opacity: 0.95;
            letter-spacing: 0.5px;
        }

        .code-input {
            width: 100%;
            padding: 1.2rem;
            font-size: 1.3rem;
            border: none;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            margin-bottom: 1.5rem;
            text-align: center;
            letter-spacing: 2px;
            font-weight: bold;
            outline: none;
            transition: all 0.3s ease;
        }

        .code-input:focus {
            transform: scale(1.02);
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
        }

        .reveal-btn {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            border: none;
            padding: 1.2rem 3rem;
            font-size: 1.2rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .reveal-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        .reveal-btn:active {
            transform: translateY(0);
        }

        .error-msg {
            color: #ff4757;
            background: rgba(255, 71, 87, 0.1);
            padding: 1rem;
            border-radius: 10px;
            margin-top: 1rem;
            border: 1px solid rgba(255, 71, 87, 0.3);
            display: none;
        }

        /* Surprise Page Styles */
        .surprise-content {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 3rem;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            animation: surpriseEntry 2s ease-out;
            position: relative;
            overflow: hidden;
        }

        @keyframes surpriseEntry {
            0% { opacity: 0; transform: scale(0.5) rotate(-10deg); }
            50% { transform: scale(1.1) rotate(5deg); }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        .birthday-title {
            font-size: 3.5rem;
            background: linear-gradient(45deg, #ff6b6b, #ffd700, #4ecdc4, #ff6b6b);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: rainbowText 4s ease-in-out infinite;
            margin-bottom: 1.5rem;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
        }

        @keyframes rainbowText {
            0%, 100% { background-position: 0% 50%; }
            25% { background-position: 100% 50%; }
            50% { background-position: 100% 100%; }
            75% { background-position: 0% 100%; }
        }

        .friend-name {
            font-size: 2.5rem;
            color: #ffd700;
            margin-bottom: 2rem;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        .birthday-message {
            font-size: 1.4rem;
            line-height: 1.8;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeInMessage 1s ease-out 1s forwards;
        }

        @keyframes fadeInMessage {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .cake {
            font-size: 4rem;
            animation: cakeWiggle 2s ease-in-out infinite;
            margin: 2rem 0;
        }

        @keyframes cakeWiggle {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(-5deg); }
            75% { transform: rotate(5deg); }
        }

        .confetti {
            position: absolute;
            top: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 10px;
            height: 10px;
            background: #ff6b6b;
            animation: confettiFall 3s linear infinite;
        }

        .confetti:nth-child(2) { left: 20%; background: #4ecdc4; animation-delay: 0.5s; }
        .confetti:nth-child(3) { left: 80%; background: #ffd700; animation-delay: 1s; }
        .confetti:nth-child(4) { left: 35%; background: #ff9ff3; animation-delay: 1.5s; }
        .confetti:nth-child(5) { left: 65%; background: #54a0ff; animation-delay: 2s; }

        @keyframes confettiFall {
            0% { transform: translateX(-50%) translateY(-100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateX(-50%) translateY(100vh) rotate(720deg); opacity: 0; }
        }

        .balloons {
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 2rem;
            animation: balloonFloat 4s ease-in-out infinite;
        }

        @keyframes balloonFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .celebration-btn {
            background: linear-gradient(45deg, #ff6b6b, #ffd700);
            color: white;
            border: none;
            padding: 1rem 2.5rem;
            font-size: 1.1rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 2rem;
            transition: all 0.3s ease;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .celebration-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 25px rgba(255, 107, 107, 0.4);
        }

        @media (max-width: 600px) {
            h1 { font-size: 2.2rem; }
            .birthday-title { font-size: 2.8rem; }
            .friend-name { font-size: 2rem; }
            .birthday-message { font-size: 1.2rem; }
        }
    </style>
</head>
<body>
    <div class="floating-shapes">
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
    </div>

    <div class="container">
        <!-- Login Section -->
        <div class="login-section" id="loginSection">
            <h1>🎁 Something Special Awaits</h1>
            <p class="subtitle">Enter the secret code to reveal your surprise</p>
            
            <input type="text" 
                   class="code-input" 
                   id="codeInput" 
                   placeholder="Enter Secret Code"
                   maxlength="20">
            
            <button class="reveal-btn" onclick="checkCode()">
                ✨ Reveal Surprise ✨
            </button>
            
            <div class="error-msg" id="errorMsg">
                Oops! That's not the right code. Try again! 🤔
            </div>
        </div>

        <!-- Surprise Section -->
        <div class="surprise-section" id="surpriseSection">
            <div class="surprise-content">
                <div class="confetti"></div>
                <div class="confetti"></div>
                <div class="confetti"></div>
                <div class="confetti"></div>
                <div class="confetti"></div>
                
                <div class="balloons">🎈🎈🎈</div>
                
                <h2 class="birthday-title">HAPPY BIRTHDAY!</h2>
                <div class="friend-name" id="friendName">Amazing Friend!</div>
                
                <div class="cake">🎂</div>
                
                <div class="birthday-message">
                    Hope your special day is filled with happiness, laughter, and all your favorite things! 
                    You deserve all the joy in the world. Here's to another year of awesome adventures 
                    and unforgettable memories! 🌟
                </div>
                
                <button class="celebration-btn" onclick="triggerCelebration()">
                    🎉 Celebrate More! 🎉
                </button>
            </div>
        </div>
    </div>

    <script>
        // Set your secret code here - you can change this to anything you want
        const SECRET_CODE = "BIRTHDAY2024";
        
        // You can customize the friend's name here
        const FRIEND_NAME = "Amazing Friend";

        function checkCode() {
            const input = document.getElementById('codeInput');
            const errorMsg = document.getElementById('errorMsg');
            const loginSection = document.getElementById('loginSection');
            const surpriseSection = document.getElementById('surpriseSection');
            
            if (input.value.toUpperCase() === SECRET_CODE) {
                // Correct code - show surprise
                errorMsg.style.display = 'none';
                loginSection.style.display = 'none';
                surpriseSection.style.display = 'block';
                
                // Update friend's name
                document.getElementById('friendName').textContent = FRIEND_NAME;
                
                // Trigger celebration effects
                setTimeout(triggerCelebration, 1000);
                
            } else {
                // Wrong code - show error
                errorMsg.style.display = 'block';
                input.value = '';
                input.style.borderColor = '#ff4757';
                
                // Reset border color after animation
                setTimeout(() => {
                    input.style.borderColor = '';
                }, 2000);
            }
        }

        function triggerCelebration() {
            // Create more confetti
            createConfetti();
            
            // Add some fun effects
            document.body.style.animation = 'none';
            document.body.offsetHeight; // Trigger reflow
            document.body.style.animation = 'gradientShift 2s ease infinite';
        }

        function createConfetti() {
            const colors = ['#ff6b6b', '#4ecdc4', '#ffd700', '#ff9ff3', '#54a0ff', '#5f27cd'];
            
            for (let i = 0; i < 50; i++) {
                setTimeout(() => {
                    const confetti = document.createElement('div');
                    confetti.style.position = 'absolute';
                    confetti.style.left = Math.random() * 100 + '%';
                    confetti.style.top = '-10px';
                    confetti.style.width = '8px';
                    confetti.style.height = '8px';
                    confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                    confetti.style.animation = 'confettiFall 3s linear forwards';
                    confetti.style.zIndex = '100';
                    
                    document.body.appendChild(confetti);
                    
                    // Remove confetti after animation
                    setTimeout(() => {
                        if (confetti.parentNode) {
                            confetti.parentNode.removeChild(confetti);
                        }
                    }, 3000);
                }, i * 100);
            }
        }

        // Allow Enter key to trigger code check
        document.getElementById('codeInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                checkCode();
            }
        });

        // Initialize
        document.getElementById('friendName').textContent = FRIEND_NAME;
    </script>
</body>
</html>
