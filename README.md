<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 25%, #4facfe 50%, #00f2fe 75%, #7dd3fc 100%);
            padding: 20px;
        }

        .container {
            display: flex;
            width: 100%;
            max-width: 1200px;
            margin: auto;
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        .image-section {
            flex: 1;
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 60px;
            position: relative;
            overflow: hidden;
        }

        .image-section::before {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            top: -100px;
            right: -100px;
        }

        .image-section::after {
            content: '';
            position: absolute;
            width: 200px;
            height: 200px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            bottom: -50px;
            left: -50px;
        }

        .flower {
            position: absolute;
            width: 40px;
            height: 40px;
            animation: float 6s ease-in-out infinite;
            opacity: 0.8;
        }

        .flower:nth-child(1) {
            top: 10%;
            left: 10%;
            animation-delay: 0s;
        }

        .flower:nth-child(2) {
            top: 60%;
            left: 5%;
            animation-delay: 2s;
            animation-duration: 7s;
        }

        .flower:nth-child(3) {
            top: 20%;
            right: 15%;
            animation-delay: 1s;
            animation-duration: 8s;
        }

        .flower:nth-child(4) {
            bottom: 15%;
            right: 10%;
            animation-delay: 3s;
        }

        .flower:nth-child(5) {
            top: 50%;
            right: 5%;
            animation-delay: 4s;
            animation-duration: 7.5s;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0) rotate(0deg);
            }
            25% {
                transform: translateY(-20px) rotate(5deg);
            }
            50% {
                transform: translateY(-10px) rotate(-5deg);
            }
            75% {
                transform: translateY(-25px) rotate(3deg);
            }
        }

        .illustration {
            width: 100%;
            max-width: 400px;
            z-index: 1;
        }

        .profile-image {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid white;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            z-index: 1;
        }

        .login-section {
            flex: 1;
            padding: 60px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        h1 {
            color: #2d3748;
            font-size: 32px;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .subtitle {
            color: #718096;
            margin-bottom: 40px;
            font-size: 14px;
        }

        .input-group {
            margin-bottom: 24px;
        }

        label {
            display: block;
            color: #4a5568;
            font-size: 14px;
            font-weight: 500;
            margin-bottom: 8px;
        }

        input {
            width: 100%;
            padding: 14px 16px;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            font-size: 15px;
            transition: all 0.3s ease;
            outline: none;
        }

        input:focus {
            border-color: #4facfe;
            box-shadow: 0 0 0 3px rgba(79, 172, 254, 0.1);
        }

        .forgot-password {
            text-align: right;
            margin-bottom: 24px;
        }

        .forgot-password a {
            color: #4facfe;
            text-decoration: none;
            font-size: 14px;
            font-weight: 500;
        }

        .forgot-password a:hover {
            text-decoration: underline;
        }

        button {
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(79, 172, 254, 0.3);
        }

        button:active {
            transform: translateY(0);
        }

        .signup-link {
            text-align: center;
            margin-top: 24px;
            color: #718096;
            font-size: 14px;
        }

        .signup-link a {
            color: #4facfe;
            text-decoration: none;
            font-weight: 600;
        }

        .signup-link a:hover {
            text-decoration: underline;
        }

        @media (max-width: 768px) {
            .container {
                flex-direction: column;
                margin: 20px;
            }

            .image-section {
                padding: 40px;
                min-height: 200px;
            }

            .login-section {
                padding: 40px 30px;
            }

            .illustration {
                max-width: 250px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="image-section">
            <!-- Animated Flowers -->
            <svg class="flower" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                <circle cx="50" cy="50" r="8" fill="#fff"/>
                <ellipse cx="50" cy="30" rx="10" ry="18" fill="#4facfe"/>
                <ellipse cx="70" cy="50" rx="18" ry="10" fill="#4facfe"/>
                <ellipse cx="50" cy="70" rx="10" ry="18" fill="#4facfe"/>
                <ellipse cx="30" cy="50" rx="18" ry="10" fill="#4facfe"/>
                <ellipse cx="65" cy="35" rx="12" ry="15" fill="#00f2fe" transform="rotate(45 65 35)"/>
                <ellipse cx="65" cy="65" rx="12" ry="15" fill="#00f2fe" transform="rotate(-45 65 65)"/>
                <ellipse cx="35" cy="35" rx="12" ry="15" fill="#00f2fe" transform="rotate(-45 35 35)"/>
                <ellipse cx="35" cy="65" rx="12" ry="15" fill="#00f2fe" transform="rotate(45 35 65)"/>
            </svg>
            
            <svg class="flower" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                <circle cx="50" cy="50" r="8" fill="#fff"/>
                <ellipse cx="50" cy="30" rx="10" ry="18" fill="#00f2fe"/>
                <ellipse cx="70" cy="50" rx="18" ry="10" fill="#00f2fe"/>
                <ellipse cx="50" cy="70" rx="10" ry="18" fill="#00f2fe"/>
                <ellipse cx="30" cy="50" rx="18" ry="10" fill="#00f2fe"/>
                <ellipse cx="65" cy="35" rx="12" ry="15" fill="#4facfe" transform="rotate(45 65 35)"/>
                <ellipse cx="65" cy="65" rx="12" ry="15" fill="#4facfe" transform="rotate(-45 65 65)"/>
                <ellipse cx="35" cy="35" rx="12" ry="15" fill="#4facfe" transform="rotate(-45 35 35)"/>
                <ellipse cx="35" cy="65" rx="12" ry="15" fill="#4facfe" transform="rotate(45 35 65)"/>
            </svg>
            
            <svg class="flower" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                <circle cx="50" cy="50" r="8" fill="#fff"/>
                <ellipse cx="50" cy="30" rx="10" ry="18" fill="#4facfe"/>
                <ellipse cx="70" cy="50" rx="18" ry="10" fill="#4facfe"/>
                <ellipse cx="50" cy="70" rx="10" ry="18" fill="#4facfe"/>
                <ellipse cx="30" cy="50" rx="18" ry="10" fill="#4facfe"/>
                <ellipse cx="65" cy="35" rx="12" ry="15" fill="#00f2fe" transform="rotate(45 65 35)"/>
                <ellipse cx="65" cy="65" rx="12" ry="15" fill="#00f2fe" transform="rotate(-45 65 65)"/>
                <ellipse cx="35" cy="35" rx="12" ry="15" fill="#00f2fe" transform="rotate(-45 35 35)"/>
                <ellipse cx="35" cy="65" rx="12" ry="15" fill="#00f2fe" transform="rotate(45 35 65)"/>
            </svg>
            
            <svg class="flower" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                <circle cx="50" cy="50" r="8" fill="#fff"/>
                <ellipse cx="50" cy="30" rx="10" ry="18" fill="#00f2fe"/>
                <ellipse cx="70" cy="50" rx="18" ry="10" fill="#00f2fe"/>
                <ellipse cx="50" cy="70" rx="10" ry="18" fill="#00f2fe"/>
                <ellipse cx="30" cy="50" rx="18" ry="10" fill="#00f2fe"/>
                <ellipse cx="65" cy="35" rx="12" ry="15" fill="#4facfe" transform="rotate(45 65 35)"/>
                <ellipse cx="65" cy="65" rx="12" ry="15" fill="#4facfe" transform="rotate(-45 65 65)"/>
                <ellipse cx="35" cy="35" rx="12" ry="15" fill="#4facfe" transform="rotate(-45 35 35)"/>
                <ellipse cx="35" cy="65" rx="12" ry="15" fill="#4facfe" transform="rotate(45 35 65)"/>
            </svg>
            
            <svg class="flower" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
                <circle cx="50" cy="50" r="8" fill="#fff"/>
                <ellipse cx="50" cy="30" rx="10" ry="18" fill="#4facfe"/>
                <ellipse cx="70" cy="50" rx="18" ry="10" fill="#4facfe"/>
                <ellipse cx="50" cy="70" rx="10" ry="18" fill="#4facfe"/>
                <ellipse cx="30" cy="50" rx="18" ry="10" fill="#4facfe"/>
                <ellipse cx="65" cy="35" rx="12" ry="15" fill="#00f2fe" transform="rotate(45 65 35)"/>
                <ellipse cx="65" cy="65" rx="12" ry="15" fill="#00f2fe" transform="rotate(-45 65 65)"/>
                <ellipse cx="35" cy="35" rx="12" ry="15" fill="#00f2fe" transform="rotate(-45 35 35)"/>
                <ellipse cx="35" cy="65" rx="12" ry="15" fill="#00f2fe" transform="rotate(45 35 65)"/>
            </svg>
            
            <input type="file" id="imageUpload" accept="image/*" style="display: none;" onchange="handleImageUpload(event)">
            <img id="profileImage" class="profile-image" src="https://via.placeholder.com/200/4facfe/ffffff?text=Upload+Photo" alt="Profile" onclick="document.getElementById('imageUpload').click()" style="cursor: pointer;">
        </div>
        
        <div class="login-section">
            <h1>Welcome Back</h1>
            <p class="subtitle">Please enter your details to sign in</p>
            
            <div class="input-group">
                <label for="email">Username</label>
                <input type="text" id="email" placeholder="Enter your username" value="Jahmela June">
            </div>
            
            <div class="input-group">
                <label for="password">Password</label>
                <input type="password" id="password" placeholder="Enter your password" value="walalang">
            </div>
            
            <div class="forgot-password">
                <a href="#">Forgot password?</a>
            </div>
            
            <button onclick="handleLogin()">Sign In</button>
            
            <div class="signup-link">
                Don't have an account? <a href="#">Sign up</a>
            </div>
        </div>
    </div>

    <script>
        function handleImageUpload(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('profileImage').src = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        }

        function handleLogin() {
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            
            if (!email || !password) {
                alert('Please fill in all fields');
                return;
            }
            
            alert('Login functionality would be connected to your backend here!');
        }

        document.getElementById('password').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                handleLogin();
            }
        });
    </script>
</body>
</html>
