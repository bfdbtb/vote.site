<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <title>윤서진 코딩 투표</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      text-align: center;
      background-color: #f2f2f2;
      padding: 50px;
    }
    h1 {
      font-size: 2em;
    }
    .button {
      padding: 15px 30px;
      font-size: 18px;
      margin: 10px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
    }
    .good {
      background-color: #4CAF50;
      color: white;
    }
    .bad {
      background-color: #f44336;
      color: white;
    }
    .results {
      margin-top: 30px;
      font-size: 1.2em;
    }
  </style>
</head>
<body>
  <h1>윤서진은 코딩을 잘한다? 못한다?</h1>
  <button class="button good" onclick="vote('good')">잘한다 👍</button>
  <button class="button bad" onclick="vote('bad')">못한다 👎</button>
  <div class="results">
    <p>잘한다: <span id="goodCount">0</span>표</p>
    <p>못한다: <span id="badCount">0</span>표</p>
  </div>

  <script>
    // 초기값 불러오기
    let goodVotes = parseInt(localStorage.getItem("goodVotes") || "0");
    let badVotes = parseInt(localStorage.getItem("badVotes") || "0");

    function updateDisplay() {
      document.getElementById("goodCount").textContent = goodVotes;
      document.getElementById("badCount").textContent = badVotes;
    }

    function vote(type) {
      if (type === 'good') {
        goodVotes++;
        localStorage.setItem("goodVotes", goodVotes);
      } else if (type === 'bad') {
        badVotes++;
        localStorage.setItem("badVotes", badVotes);
      }
      updateDisplay();
    }

    // 초기 화면 업데이트
    updateDisplay();
  </script>
</body>
</html>
