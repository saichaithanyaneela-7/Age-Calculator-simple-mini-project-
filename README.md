

<html>
<head>
  <title>Age Calculator</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #eaf2f8;
      text-align: center;
      padding: 50px;
    }

    .container {
      background: white;
      padding: 30px;
      max-width: 400px;
      margin: auto;
      border-radius: 10px;
      box-shadow: 0 0 10px #bbb;
    }

    h2 {
      color: #007bff;
    }

    input, button {
      padding: 10px;
      margin: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      background: #007bff;
      color: white;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background: #0056b3;
    }

    #result {
      color: #198754;
      font-size: 18px;
      font-weight: bold;
      margin-top: 20px;
    }

    @media (max-width: 480px) {
      body {
        padding: 20px 10px;
      }

      .container {
        padding: 20px 10px;
      }
    }
  </style>
</head>

<body>
  <div class="container">
    <h2>Age Calculator</h2>

    <label for="birthdate">Enter your birthdate:</label>
    <br>
    <input type="date" id="birthdate">
    <br>

    <button onclick="calculateAge()">Calculate Age</button>

    <p id="result"></p>
  </div>

  <script>
    // Set today's date as the maximum birthdate
    document.getElementById("birthdate").max =
      new Date().toLocaleDateString("en-CA");

    function calculateAge() {
      const input = document.getElementById("birthdate").value;
      const result = document.getElementById("result");

      if (!input) {
        result.innerText = "Please enter your birthdate.";
        return;
      }

      const birthdate = new Date(input + "T00:00:00");
      const today = new Date();
      today.setHours(0, 0, 0, 0);

      if (birthdate > today) {
        result.innerText = "Birthdate cannot be in the future.";
        return;
      }

      let years = today.getFullYear() - birthdate.getFullYear();
      let months = today.getMonth() - birthdate.getMonth();
      let days = today.getDate() - birthdate.getDate();

      if (days < 0) {
        months--;

        const previousMonthDays = new Date(
          today.getFullYear(),
          today.getMonth(),
          0
        ).getDate();

        days += previousMonthDays;
      }

      if (months < 0) {
        years--;
        months += 12;
      }

      result.innerText =
        `You are ${years} years, ${months} months, and ${days} days old.`;
    }
  </script>
</body>
</html>
