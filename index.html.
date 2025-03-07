<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Culture Générale</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; margin: 20px; }
        .question { font-size: 20px; margin-bottom: 20px; }
        .answers button { display: block; margin: 10px auto; padding: 10px; width: 200px; cursor: pointer; }
        .correct { background-color: green; color: white; }
        .wrong { background-color: red; color: white; }
        .explanation { margin-top: 20px; font-size: 16px; }
        .score { margin-top: 20px; font-size: 18px; font-weight: bold; }
    </style>
</head>
<body>
    <h1>Quiz Culture Générale</h1>
    <div class="question" id="question">Chargement...</div>
    <div class="answers" id="answers"></div>
    <div class="explanation" id="explanation"></div>
    <div class="score">Score: <span id="score">0</span></div>
    
    <script>
        let score = 0;
        const questions = [
            {
                question: "Quelle est la capitale de la France ?",
                answers: ["Londres", "Berlin", "Paris", "Madrid"],
                correct: 2,
                explanation: "Paris est la capitale de la France.",
                link: "https://fr.wikipedia.org/wiki/Paris"
            },
            {
                question: "Qui a peint La Joconde ?",
                answers: ["Vincent Van Gogh", "Léonard de Vinci", "Pablo Picasso", "Claude Monet"],
                correct: 1,
                explanation: "Léonard de Vinci a peint La Joconde.",
                link: "https://fr.wikipedia.org/wiki/La_Joconde"
            }
        ];

        let currentQuestionIndex = 0;
        
        function loadQuestion() {
            const q = questions[currentQuestionIndex];
            document.getElementById("question").textContent = q.question;
            const answersDiv = document.getElementById("answers");
            answersDiv.innerHTML = "";
            
            q.answers.forEach((answer, index) => {
                const button = document.createElement("button");
                button.textContent = answer;
                button.onclick = () => checkAnswer(index);
                answersDiv.appendChild(button);
            });
        }

        function checkAnswer(selected) {
            const q = questions[currentQuestionIndex];
            const buttons = document.querySelectorAll(".answers button");
            
            buttons[q.correct].classList.add("correct");
            if (selected !== q.correct) {
                buttons[selected].classList.add("wrong");
                score -= 1;
            } else {
                score += 2;
            }
            
            document.getElementById("score").textContent = score;
            document.getElementById("explanation").innerHTML = `${q.explanation} <br> <a href="${q.link}" target="_blank">En savoir plus</a>`;
            
            setTimeout(() => {
                currentQuestionIndex = (currentQuestionIndex + 1) % questions.length;
                document.getElementById("explanation").innerHTML = "";
                loadQuestion();
            }, 3000);
        }

        loadQuestion();
    </script>
</body>
</html>
