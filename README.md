# Web-Dev-Internship-prjct
Age Calculating Site
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            text-align: center;
            padding: 50px;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            margin: auto;
        }
        input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            background: #ff758c;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #ff5e78;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Age Calculator</h2>
        <input type="date" id="dob">
        <button onclick="calculateAge()">Calculate Age</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculateAge() {
            let dob = document.getElementById('dob').value;
            if (!dob) {
                document.getElementById('result').innerText = "Please select your date of birth.";
                return;
            }
            let dobDate = new Date(dob);
            let today = new Date();
            
            let years = today.getFullYear() - dobDate.getFullYear();
            let months = today.getMonth() - dobDate.getMonth();
            let days = today.getDate() - dobDate.getDate();
            
            if (days < 0) {
                months--;
                days += new Date(today.getFullYear(), today.getMonth(), 0).getDate();
            }
            if (months < 0) {
                years--;
                months += 12;
            }
            
            document.getElementById('result').innerText = `You are ${years} years, ${months} months, and ${days} days old.`;
        }
    </script>
</body>
</html>
