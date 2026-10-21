# Age-Calculator-simple-mini-project-

<!DOCTYPE html>
<html>
<head>
  <title>Age Calculator</title>
</head>
<body>
  <h2>Age Calculator</h2>
  <label for="birthdate">Enter your birthdate:</label>
  <input type="date" id="birthdate">
  <button onclick="calculateAge()">Calculate Age</button>

  <p id="result"></p>

  <script>
    function calculateAge() {
      const birthdateInput = document.getElementById("birthdate").value;
      if (!birthdateInput) {
        document.getElementById("result").innerText = "Please enter a valid birthdate.";
        return;
      }

      const birthdate = new Date(birthdateInput);
      const today = new Date();

      let age = today.getFullYear() - birthdate.getFullYear();
      const m = today.getMonth() - birthdate.getMonth();

      if (m < 0 || (m === 0 && today.getDate() < birthdate.getDate())) {
        age--;
      }

      document.getElementById("result").innerText = `You are ${age} years old.`;
    }
  </script>
</body>
</html>
