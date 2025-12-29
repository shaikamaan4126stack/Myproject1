<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Responsive Quiz App</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: Arial, Helvetica, sans-serif;
}

body{
    min-height:100vh;
    background:linear-gradient(135deg,#0f2027,#203a43);
    display:flex;
    justify-content:center;
    align-items:flex-start;
    padding:20px;
    color:#fff;
}

/* MAIN WRAPPER */
.quiz-wrapper{
    width:100%;
    max-width:900px;
}

/* SCORE BOARD */
.score-board{
    background:rgba(0,0,0,0.5);
    padding:15px 20px;
    margin-bottom:25px;
    border-radius:14px;
    border:2px solid #fff;
    display:flex;
    justify-content:space-between;
    align-items:center;
    flex-wrap:wrap;
    gap:10px;
    animation:slide 1s ease;
}

.score-board h2{
    font-size:clamp(18px,4vw,24px);
    letter-spacing:2px;
}

.score{
    font-size:clamp(14px,3vw,18px);
    font-weight:bold;
}

/* QUIZ CARD */
.quiz{
    background:rgba(255,255,255,0.12);
    padding:20px;
    border-radius:18px;
    border:2px solid rgba(255,255,255,0.4);
    box-shadow:0 20px 50px rgba(0,0,0,0.5);
}

/* QUESTION */
.question{
    margin-bottom:22px;
    padding:15px;
    border-radius:12px;
    border:2px dashed rgba(255,255,255,0.4);
    transition:0.3s;
}

.question:hover{
    transform:scale(1.02);
}

.question p{
    font-size:clamp(15px,3vw,18px);
    margin-bottom:12px;
}

/* OPTIONS */
.options{
    display:flex;
    flex-direction:column;
    gap:10px;
}

input{
    display:none;
}

label{
    padding:10px 15px;
    background:rgba(0,0,0,0.35);
    border-radius:8px;
    cursor:pointer;
    transition:0.3s;
}

label:hover{
    background:#fff;
    color:#000;
    transform:translateX(6px);
}

/* CORRECT & WRONG */
.correct:checked + label{
    background:#2ecc71;
    color:#000;
    font-weight:bold;
    pointer-events:none;
    animation:correct 0.4s;
}

.wrong:checked + label{
    background:#e74c3c;
    pointer-events:none;
    animation:shake 0.3s;
}

/* ANIMATIONS */
@keyframes shake{
    0%{transform:translateX(0);}
    25%{transform:translateX(-4px);}
    50%{transform:translateX(4px);}
}

@keyframes correct{
    0%{transform:scale(1);}
    50%{transform:scale(1.1);}
    100%{transform:scale(1);}
}

@keyframes slide{
    from{transform:translateY(-30px);opacity:0;}
    to{transform:translateY(0);opacity:1;}
}

/* RESPONSIVE */
@media(max-width:600px){
    .score-board{
        flex-direction:column;
        text-align:center;
    }

    .quiz{
        padding:15px;
    }

    label{
        font-size:14px;
    }
}
</style>
</head>

<body>

<div class="quiz-wrapper">

    <div class="score-board">
        <h2>Quiz Score</h2>
        <div class="score">✔ Select the Correct Answer</div>
    </div>

    <div class="quiz">

        <div class="question">
            <p>1. HTML stands for?</p>
            <div class="options">
                <input type="radio" name="q1" id="q1a" class="wrong">
                <label for="q1a">High Text Machine Language</label>

                <input type="radio" name="q1" id="q1b" class="correct">
                <label for="q1b">Hyper Text Markup Language</label>

                <input type="radio" name="q1" id="q1c" class="wrong">
                <label for="q1c">High Trainer Marking Language</label>
            </div>
        </div>

        <div class="question">
            <p>2. CSS stands for?</p>
            <div class="options">
                <input type="radio" name="q2" id="q2a" class="correct">
                <label for="q2a">Cascading Style Sheets</label>

                <input type="radio" name="q2" id="q2b" class="wrong">
                <label for="q2b">Creative Style System</label>

                <input type="radio" name="q2" id="q2c" class="wrong">
                <label for="q2c">Color Style Sheet</label>
            </div>
        </div>

        <div class="question">
            <p>3. Which property makes layout flexible?</p>
            <div class="options">
                <input type="radio" name="q3" id="q3a" class="correct">
                <label for="q3a">display: flex</label>

                <input type="radio" name="q3" id="q3b" class="wrong">
                <label for="q3b">position: absolute</label>

                <input type="radio" name="q3" id="q3c" class="wrong">
                <label for="q3c">float: left</label>
            </div>
        </div>

        <!-- Remaining questions stay SAME -->

    </div>
</div>

</body>
</html>
