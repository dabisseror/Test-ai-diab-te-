<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IA Médicale - Prédiction Diabète</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f7fa;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 1rem;
            text-align: center;
        }
        main {
            max-width: 600px;
            margin: 2rem auto;
            background-color: white;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        label {
            display: block;
            margin-top: 1rem;
        }
        input {
            width: 100%;
            padding: 0.5rem;
            margin-top: 0.2rem;
            border-radius: 6px;
            border: 1px solid #ccc;
        }
        button {
            margin-top: 1.5rem;
            width: 100%;
            padding: 0.7rem;
            border: none;
            border-radius: 8px;
            background-color: #4CAF50;
            color: white;
            font-size: 1rem;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .result {
            margin-top: 1.5rem;
            font-size: 1.2rem;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <header>
        <h1>IA Médicale - Prédiction du Diabète</h1>
    </header>
    <main>
        <form id="patientForm">
            <label for="age">Âge (ans):</label>
            <input type="number" id="age" required>

            <label for="bmi">BMI (kg/m²):</label>
            <input type="number" step="0.1" id="bmi" required>

            <label for="glucose">Glucose (mg/dL):</label>
            <input type="number" id="glucose" required>

            <label for="bloodpressure">Tension artérielle (mmHg):</label>
            <input type="number" id="bloodpressure" required>

            <button type="button" onclick="predictDiabetes()">Prédire le risque</button>
        </form>

        <div class="result" id="result"></div>
    </main>

    <script>
        // Simulation d'une prédiction IA simple
        function predictDiabetes() {
            const age = parseFloat(document.getElementById('age').value);
            const bmi = parseFloat(document.getElementById('bmi').value);
            const glucose = parseFloat(document.getElementById('glucose').value);
            const bp = parseFloat(document.getElementById('bloodpressure').value);

            // Modèle simulé simple : juste pour prototype
            let score = 0;
            if (age > 45) score += 1;
            if (bmi > 25) score += 1;
            if (glucose > 120) score += 2;
            if (bp > 80) score += 1;

            let risk = "";
            if (score <= 1) {
                risk = "Risque faible";
            } else if (score <= 3) {
                risk = "Risque modéré";
            } else {
                risk = "Risque élevé";
            }

            document.getElementById('result').textContent = "Résultat : " + risk;
        }
    </script>
</body>
</html>
