# Yamini-tech
Gamified learning platform including mood detection system 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MoodLearn - Gamified Learning</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>🎓 MoodLearn</h1>
    <p>Learn Smarter with Your Mood!</p>
  </header>

  <section class="mood">
    <h2>How are you feeling today?</h2>
    <div class="emojis">
      <button onclick="setMood('😊')">😊</button>
      <button onclick="setMood('😐')">😐</button>
      <button onclick="setMood('😔')">😔</button>
      <button onclick="setMood('😡')">😡</button>
    </div>
    <p id="moodText"></p>
  </section>

  <section class="learn">
    <h2>Today's Lesson</h2>
    <p>Answer quiz questions to earn XP!</p>
    <button onclick="startQuiz()">Start Quiz</button>
  </section>

  <section id="quiz" class="hidden">
    <h3>What is 5 + 3?</h3>
    <button onclick="checkAnswer('wrong')">6</button>
    <button onclick="checkAnswer('right')">8</button>
    <button onclick="checkAnswer('wrong')">10</button>
    <p id="result"></p>
  </section>

  <footer>
    <p>Made with ❤️ by You</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>

body {
  font-family: 'Poppins', sans-serif;
  text-align: center;
  background: linear-gradient(to right, #a1c4fd, #c2e9fb);
  color: #333;
  margin: 0;
  padding: 0;
}

header {
  background-color: #4a90e2;
  color: white;
  padding: 20px;
}

button {
  font-size: 25px;
  margin: 10px;
  padding: 10px 20px;
  border-radius: 10px;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #f0f0f0;
}

.hidden {
  display: none;
  
}

footer {
  margin-top: 30px;
  background-color: #4a90e2;
  color: white;
  padding: 10px;
}

function setMood(mood) {
  document.getElementById("moodText").innerText = "Your mood: " + mood;
  alert("Mood detected: " + mood);
}

function startQuiz() {
  document.getElementById("quiz").classList.remove("hidden");
}

function checkAnswer(choice) {
  let result = document.getElementById("result");
  if (choice === 'right') {
    result.innerText = "✅ Correct! You earned 10 XP!";
  } else {
    result.innerText = "❌ Oops! Try again.";
  }
}
