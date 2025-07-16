# index.html<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Worksheet Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background: #f9f9f9;
      color: #333;
    }
    .container {
      background: white;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 600px;
      margin: auto;
    }
    h1 {
      text-align: center;
      color: #4CAF50;
    }
    select, button {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      font-size: 1rem;
    }
    .worksheet {
      margin-top: 2rem;
      padding: 1rem;
      border: 1px dashed #ccc;
      background: #f1f1f1;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>📝 Worksheet Generator</h1>
    <label for="subject">Select Subject:</label>
    <select id="subject">
      <option value="math">Math</option>
      <option value="gk">General Knowledge</option>
      <option value="english">English</option>
    </select>

    <label for="grade">Select Grade:</label>
    <select id="grade">
      <option value="1">Class 1</option>
      <option value="2">Class 2</option>
      <option value="3">Class 3</option>
      <option value="4">Class 4</option>
      <option value="5">Class 5</option>
      <option value="6">Class 6</option>
      <option value="7">Class 7</option>
      <option value="8">Class 8</option>
    </select>

    <button onclick="generateWorksheet()">Generate Worksheet</button>

    <div class="worksheet" id="worksheet"></div>
  </div>

  <script>
    const worksheets = {
      math: [
        "Solve: 12 + 8 = ?",
        "Find the LCM of 6 and 8",
        "Convert 3/4 into a decimal",
        "Write Roman numeral for 40"
      ],
      gk: [
        "What is the capital of India?",
        "Name the largest planet in our solar system.",
        "Who wrote the National Anthem of India?",
        "What is the currency of Japan?"
      ],
      english: [
        "Underline the noun: The cat sat on the mat.",
        "Write the plural of 'child'.",
        "Fill in the blank: She ____ going to school.",
        "Rearrange to form a sentence: dog / barking / is / the"
      ]
    };

    function generateWorksheet() {
      const subject = document.getElementById('subject').value;
      const grade = document.getElementById('grade').value;
      const questions = worksheets[subject];

      let output = `<h3>Subject: ${subject.toUpperCase()} | Grade: ${grade}</h3><ol>`;
      questions.forEach(q => {
        output += `<li>${q}</li>`;
      });
      output += '</ol>';

      document.getElementById('worksheet').innerHTML = output;
    }
  </script>
</body>
</html>
