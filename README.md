# AI-powered-Portfolio-website
This is my Portfolio Website made with HTML, CSS and JS, integrated with an AI chatbot.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mounisha's Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
            transition: background-color 0.3s, color 0.3s;
        }

        body {
            line-height: 1.6;
            color: #333;
            background-color: #f4f4f4;
        }

        body.dark-theme {
            color: #e0e0e0;
            background-color: #1a1a1a;
        }

        /* Navigation */
        nav {
            background-color: #fff;
            padding: 1rem 2rem;
            position: fixed;
            width: 100%;
            top: 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            z-index: 1000;
        }

        body.dark-theme nav {
            background-color: #2c2c2c;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #007bff;
        }

        body.dark-theme .logo {
            color: #00c4b4;
        }

        .nav-links a {
            margin-left: 1.5rem;
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }

        body.dark-theme .nav-links a {
            color: #e0e0e0;
        }

        .nav-links a:hover {
            color: #007bff;
        }

        body.dark-theme .nav-links a:hover {
            color: #00c4b4;
        }

        .theme-toggle {
            background: none;
            border: none;
            font-size: 1.2rem;
            cursor: pointer;
            color: #333;
        }

        body.dark-theme .theme-toggle {
            color: #e0e0e0;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #007bff, #00c4b4);
            color: #fff;
            text-align: center;
            padding: 2rem;
        }

        body.dark-theme .hero {
            background: linear-gradient(135deg, #004085, #007b7b);
        }

        .hero-content h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .hero-content p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
        }

        /* About Section */
        .about {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            text-align: center;
        }

        body.dark-theme .about {
            background-color: #2c2c2c;
        }

        .about h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .about p {
            max-width: 800px;
            margin: 0 auto;
            font-size: 1.1rem;
        }

        .profile-pic {
            width: 250px;
            height: 400px;
            object-fit: cover;
            border-radius: 10px;
            margin: 1rem auto;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        body.dark-theme .profile-pic {
            box-shadow: 0 2px 10px rgba(255, 255, 255, 0.1);
        }

        /* Projects Section */
        .projects {
            padding: 4rem 2rem;
            background-color: #fff;
        }

        body.dark-theme .projects {
            background-color: #222222;
        }

        .projects h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 2rem;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .project-card {
            background-color: #f9f9f9;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
        }

        body.dark-theme .project-card {
            background-color: #333333;
            box-shadow: 0 2px 10px rgba(255, 255, 255, 0.1);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        }

        body.dark-theme .project-card:hover {
            box-shadow: 0 8px 20px rgba(255, 255, 255, 0.2);
        }

        .project-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: opacity 0.3s;
        }

        .project-card:hover img {
            opacity: 0.7;
        }

        .project-info {
            padding: 1.5rem;
        }

        .project-info h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .project-info p {
            color: #666;
        }

        body.dark-theme .project-info p {
            color: #b0b0b0;
        }

        /* Contact Section */
        .contact {
            padding: 4rem 2rem;
            text-align: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        body.dark-theme .contact {
            background-color: #2c2c2c;
        }

        .contact h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .contact p {
            font-size: 1.1rem;
            margin-bottom: 2rem;
        }

        .contact a {
            display: inline-block;
            padding: 0.75rem 1.5rem;
            background-color: #007bff;
            color: #fff;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s;
        }

        body.dark-theme .contact a {
            background-color: #00c4b4;
        }

        .contact a:hover {
            background-color: #0056b3;
        }

        body.dark-theme .contact a:hover {
            background-color: #008b83;
        }

        /* Chat Bubble */
        .chat-bubble {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background-color: #007bff;
            color: #fff;
            padding: 1rem 1.5rem;
            border-radius: 50px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            cursor: pointer;
            font-size: 1rem;
            z-index: 1000;
            transition: transform 0.3s, background-color 0.3s;
        }

        body.dark-theme .chat-bubble {
            background-color: #00c4b4;
            box-shadow: 0 2px 10px rgba(255, 255, 255, 0.2);
        }

        .chat-bubble:hover {
            transform: scale(1.1);
        }

        /* Chat Overlay */
        .chat-overlay {
            display: none;
            position: fixed;
            bottom: 80px;
            right: 2rem;
            width: 350px;
            max-height: 500px;
            background-color: #fff;
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            z-index: 1000;
            flex-direction: column;
            overflow: hidden;
        }

        body.dark-theme .chat-overlay {
            background-color: #2c2c2c;
        }

        .chat-overlay.active {
            display: flex;
        }

        .chat-header {
            background-color: #007bff;
            color: #fff;
            padding: 1rem;
            font-size: 1.2rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        body.dark-theme .chat-header {
            background-color: #00c4b4;
        }

        .chat-header .profile-pic {
            width: 40px;
            height: 30px;
            object-fit: cover;
            border-radius: 5px;
        }

        .chat-header .close-btn {
            cursor: pointer;
            font-size: 1.5rem;
            margin-left: auto;
        }

        .chat-body {
            flex: 1;
            padding: 1rem;
            overflow-y: auto;
            background-color: #f9f9f9;
        }

        body.dark-theme .chat-body {
            background-color: #333333;
        }

        .chat-message {
            margin-bottom: 1rem;
            display: flex;
            flex-direction: column;
        }

        .user {
            align-items: flex-end;
        }

        .ai {
            align-items: flex-start;
        }

        .chat-message .message-content {
            max-width: 70%;
            padding: 0.75rem;
            border-radius: 10px;
            font-size: 0.9rem;
        }

        .user .message-content {
            background-color: #007bff;
            color: #fff;
        }

        body.dark-theme .user .message-content {
            background-color: #00c4b4;
        }

        .ai .message-content {
            background-color: #e0e0e0;
            color: #333;
        }

        body.dark-theme .ai .message-content {
            background-color: #4a4a4a;
            color: #e0e0e0;
        }

        .chat-footer {
            padding: 1rem;
            border-top: 1px solid #ddd;
            display: flex;
            align-items: center;
        }

        body.dark-theme .chat-footer {
            border-top: 1px solid #555;
        }

        .chat-footer input {
            flex: 1;
            padding: 0.5rem;
            border: 1px solid #ddd;
            border-radius: 20px;
            outline: none;
            font-size: 0.9rem;
        }

        body.dark-theme .chat-footer input {
            border: 1px solid #555;
            background-color: #3c3c3c;
            color: #e0e0e0;
        }

        .chat-footer button {
            margin-left: 0.5rem;
            padding: 0.5rem 1rem;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        body.dark-theme .chat-footer button {
            background-color: #00c4b4;
        }

        .chat-footer button:hover {
            background-color: #0056b3;
        }

        body.dark-theme .chat-footer button:hover {
            background-color: #008b83;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2rem;
            }

            .hero-content p {
                font-size: 1rem;
            }

            .nav-links {
                display: none;
            }

            .nav-container {
                justify-content: space-between;
            }

            .about h2,
            .projects h2,
            .contact h2 {
                font-size: 2rem;
            }

            .chat-bubble {
                padding: 0.75rem 1rem;
                font-size: 0.9rem;
            }

            .chat-overlay {
                width: 90%;
                max-height: 400px;
                bottom: 70px;
                right: 1rem;
            }

            .profile-pic {
                width: 150px;
                height: 100px;
            }
        }

        @media (max-width: 480px) {
            .hero-content h1 {
                font-size: 1.5rem;
            }

            .project-card img {
                height: 150px;
            }

            .chat-bubble {
                bottom: 1rem;
                right: 1rem;
            }

            .chat-overlay {
                width: 95%;
                bottom: 60px;
            }

            .chat-header {
                font-size: 1rem;
            }

            .chat-header .profile-pic {
                width: 50px;
                height: 200px;
            }

            .chat-footer input {
                font-size: 0.8rem;
            }

            .chat-footer button {
                padding: 0.4rem 0.8rem;
                font-size: 0.8rem;
            }

            .profile-pic {
                width: 120px;
                height: 80px;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">My Portfolio</div>
            <div class="nav-links">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#projects">Projects</a>
                <a href="#contact">Contact</a>
                <button class="theme-toggle" onclick="toggleTheme()">🌙</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Welcome to My Portfolio</h1>
            <p>Hi!This is Mounisha!
            I'm a Front-end developer creating innovative solutions. Explore my work and let's connect!</p>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <h2>About Me</h2>
        <img src="https://i.ibb.co/3y3fWfnT/Whats-App-Image-2025-06-28-at-00-13-33.jpg" alt="Profile Picture" class="profile-pic">
        <p id="myDescription">This is Mounisha Saha! A final year student pursuing my Bachelors in Computer Application from Institute of Engineering & Management. An Idiosyncratic(STRESS ON IDIOSYNCRATIC), non-conformist and driven indiviual with a keen interest in Front-End Development. I happen be familiar with C, C++, SQL along with CS Fundamentals including DBMS,OS, OOPS, Software Engineering and Computer Networks.Besides, academics I enjoy writing articles for 'The Telegraph's' esteemed daily. A voracious reader and public speaker and a feminist at Heart. Oh! nearly forgot, also a party of the Departental Band where I am a vocalist.;</p>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <h2>My Projects</h2>
        <div class="project-grid">
            <div class="project-card">
                <img src="https://i.ibb.co/KxpVFkPV/Whats-App-Image-2025-06-29-at-00-17-19.jpg" alt="Portfolio Website">
                <div class="project-info">
                    <h3>Dynamic Portfolio</h3>
                    <p>A sleek portfolio website,integrated with AI built with HTML, CSS, and JavaScript, showcasing responsive design and modern UI.</p>
                </div>
            </div>
            <div class="project-card">
                <img src="https://source.unsplash.com/random/300x200?dashboard" alt="Analytics Dashboard">
                <div class="project-info">
                    <h3>Analytics Dashboard</h3>
                    <p>An interactive dashboard for data visualization, leveraging JavaScript frameworks for real-time insights.</p>
                </div>
            </div>
            <div class="project-card">
                <img src="https://i.ibb.co/8ZqN9qD/Whats-App-Image-2025-06-28-at-22-53-36.jpg" alt="E-Commerce Store">
                <div class="project-info">
                    <h3>Email validator</h3>
                    <p>Built with Html, css and Javascript.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <h2>Get in Touch</h2>
        <p>Interested in collaborating or have a project in mind? Feel free to reach out!</p>
        <a href="mailto:example@email.com">Contact Me</a>
    </section>

    <!-- Chat Bubble -->
    <div class="chat-bubble" onclick="toggleChat()">Ask anything about me</div>

    <!-- Chat Overlay -->
    <div class="chat-overlay" id="chatOverlay">
        <div class="chat-header">
            <img src="https://i.ibb.co/3y3fWfnT/Whats-App-Image-2025-06-28-at-00-13-33.jpg" alt="Profile Picture" class="profile-pic">
            <span>Chat with Me</span>
            <span class="close-btn" onclick="toggleChat()">×</span>
        </div>
        <div class="chat-body" id="chatMessages">
            <div class="chat-message ai">
                <div class="message-content">Hi, This is Mounisha Saha, what do you want to know about me?</div>
            </div>
        </div>
        <div class="chat-footer">
            <input type="text" id="chatInput" placeholder="Type your message..." />
            <button onclick="sendMessage()">Send</button>
        </div>
    </div>
</body>
<script type="module">
// Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/11.9.1/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/11.9.1/firebase-analytics.js";
  // TODO: Add SDKs for Firebase products that you want to use
  // https://firebase.google.com/docs/web/setup#available-libraries

  // Your web app's Firebase configuration
  // For Firebase JS SDK v7.20.0 and later, measurementId is optional
  const firebaseConfig = {
    apiKey: "AIzaSyCmA4lxwlkFyuRZ9QCxVqEn4bzqR9Cb_ag",
    authDomain: "aimounishaportfolio.firebaseapp.com",
    projectId: "aimounishaportfolio",
    storageBucket: "aimounishaportfolio.firebasestorage.app",
    messagingSenderId: "716871069581",
    appId: "1:716871069581:web:a02451b1587d3d166817c4",
    measurementId: "G-MP3CXVJF4X"
  };

  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
</script>

    <script>
        const chatOverlay = document.getElementById('chatOverlay');
        const chatMessages = document.getElementById('chatMessages');
        const chatInput = document.getElementById('chatInput');
        const themeToggle = document.querySelector('.theme-toggle');
        const myFullName = "Mounisha Saha"; // Replace with your full name
        const myDescription = "This is Mounisha Saha! A final year student pursuing my Bachelors in Computer Application from Institute of Engineering & Management. An Idiosyncratic(STRESS ON IDIOSYNCRATIC), non-conformist and driven indiviual with a keen interest in Front-End Development. I happen be familiar with C, C++, SQL along with CS Fundamentals including DBMS,OS, OOPS, Software Engineering and Computer Networks.Besides, academics I enjoy writing articles for 'The Telegraph's' esteemed daily. A voracious reader and public speaker and a feminist at Heart. Oh! nearly forgot, also a party of the Departental Band where I am a vocalist. P.S- So many things, It's hard to keep track. Thanks for asking anyway! BEFORE I FORGET, I AM A BIG ADELE AND BON JOVI FAN. My Hobbie are like any other cranky teenager although I am not one now. I enjoy my leisure time listening to songs, watching netflix, a big time movie buff, playing the guitar and sleep. LOL";

        function toggleTheme() {
            document.body.classList.toggle('dark-theme');
            themeToggle.textContent = document.body.classList.contains('dark-theme') ? '☀️' : '🌙';
        }

        function toggleChat() {
            chatOverlay.classList.toggle('active');
            if (chatOverlay.classList.contains('active')) {
                chatMessages.innerHTML = `<div class="chat-message ai"><div class="message-content">Hi, I am ${myFullName}, what do you want to know about me?</div></div>`;
            }
        }

        async function sendMessage() {
            const messageText = chatInput.value.trim();
            if (!messageText) return ;{
                // Add user message
                const userMessage = document.createElement('div');
                userMessage.className = 'chat-message user';
                userMessage.innerHTML = `<div class="message-content">${messageText}</div>`;
                chatMessages.appendChild(userMessage);
                chatInput.value='';
                chatMessages.scrollTop= chatMessages.scrollHeight;

                // Add typing indicator
                const typingIndicator = document.createElement('div');
                typingIndicator.className = 'chat-message ai';
                typingIndicator.innerHTML = `<div class="message-content">Typing...</div>`;
                chatMessages.appendChild(typingIndicator);
                chatMessages.scrollTop = chatMessages.scrollHeight;

                // Simulate API call to Gemini
                 try {
                const apiKey = "AIzaSyBS9xXul9gr-jCpJvg7Zr4sL_0LoK66Xpc"; // Replace with your actual API key
    
                   const response= await fetch('https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key='+apiKey, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                        },
                        body: JSON.stringify({
                            contents: [{
                                parts: [{
                                    text: `User message: ${messageText}. Reply naturally to the user message and if required then answer based on: ${myDescription} or just simply give friendly reply. And reply in a way that ${myFullName} is himself talking. Reply in short sentences`
                                }]
                            }]
                        })
                    })
                    .then(response => response.json())
                    .then(data => {
                        // Remove typing indicator
                        chatMessages.removeChild(typingIndicator);
                        const aiResponse = data.candidates[0].content.parts[0].text;
                        setTimeout(() => {
                            const aiMessage = document.createElement('div');
                            aiMessage.className = 'chat-message ai';
                            aiMessage.innerHTML = `<div class="message-content">${aiResponse}</div>`;
                            chatMessages.appendChild(aiMessage);
                            chatMessages.scrollTop = chatMessages.scrollHeight;
                        }, 500);
                    })
                    .catch(error => {
                        console.error('Error fetching API:', error);
                        // Remove typing indicator
                        chatMessages.removeChild(typingIndicator);
                        // Fallback mock response if API fails
                        const mockResponse = {
                            candidates: [{
                                content: {
                                    parts: [{
                                        text: `Hey, I'm ${myFullName}. Something went wrong, but I'm here! Try asking again.`
                                    }]
                                }
                            }]
                        };
                        setTimeout(() => {
                            const aiMessage = document.createElement('div');
                            aiMessage.className = 'chat-message ai';
                            aiMessage.innerHTML = `<div class="message-content">${mockResponse.candidates[0].content.parts[0].text}</div>`;
                            chatMessages.appendChild(aiMessage);
                            chatMessages.scrollTop = chatMessages.scrollHeight;
                        }, 500);
                    });
                } catch (error) {
                    console.error('Fetch error:', error);
                    // Remove typing indicator
                    chatMessages.removeChild(typingIndicator);
                }

                chatInput.value = '';
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
        }

        // Allow sending message with Enter key
        chatInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                sendMessage();
            }
        });
    </script>
</body>
</html>
