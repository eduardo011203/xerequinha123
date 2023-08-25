<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
  body {
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
    position: relative;
  }
  #question {
    text-align: center;
    font-size: 24px;
    margin-bottom: 20px;
  }
  .box {
    display: inline-block;
    width: 100px;
    height: 50px;
    margin: 10px;
    text-align: center;
    line-height: 50px;
    cursor: pointer;
    border-radius: 5px;
    font-weight: bold;
    transition: transform 0.3s;
  }
  #yes {
    background-color: green;
    color: white;
  }
  #no {
    background-color: red;
    color: white;
  }
  #message {
    display: none;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 24px;
    text-align: center;
    color: white;
  }
</style>
<title>Xerequinha</title>
</head>
<body>
  <div id="question">Tem xerequinha hoje, amor?</div>
  <div class="box" id="yes">Sim</div>
  <div class="box" id="no">Não</div>
  <div id="message">Escolha certa, hoje te parto no meio</div>
  <script>
    const noBox = document.getElementById("no");
    const yesBox = document.getElementById("yes");
    const message = document.getElementById("message");

    let noBoxClicked = false;

    noBox.addEventListener("click", () => {
      if (!noBoxClicked) {
        noBox.style.transform = `translate(${Math.random() * 80 - 40}px, ${Math.random() * 80 - 40}px)`;
        noBoxClicked = true;
      }
    });

    yesBox.addEventListener("click", () => {
      document.body.style.backgroundColor = "black";
      document.getElementById("question").style.display = "none";
      yesBox.style.display = "none";
      noBox.style.display = "none";
      message.style.display = "block";
    });
  </script>
</body>
</html>
