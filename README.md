<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binomo Signal</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html, body {
            height: 100%;
            background-color: #0d1b2a;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
        }
        h1 {
            font-size: 36px;
            font-weight: bold;
            color: red;
        }
        .subtitle {
            font-size: 16px;
            font-style: italic;
            color: #00c3ff;
            text-shadow: 1px 1px 5px #00c3ff;
        }
        .container {
            max-width: 400px;
            margin: auto;
            background-color: #1e293b;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 4px 8px rgba(0, 195, 255, 0.3);
        }
        .label {
            text-align: left;
            font-weight: bold;
            margin-top: 15px;
        }
        select, button {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            margin-top: 5px;
            border-radius: 5px;
            border: none;
        }
        select {
            background-color: #252525;
            color: white;
        }
        .generate-btn {
            margin-top: 20px;
            background-color: red;
            color: white;
            font-size: 20px;
            cursor: pointer;
        }
        .generate-btn:hover {
            background-color: darkred;
        }
        #signal-container {
            margin-top: 20px;
            font-size: 16px;
            font-weight: bold;
        }
        .signal-box {
            border: 1px solid lightgreen;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            background-color: #2b3e50;
        }
    </style>
</head>
<body>

    <h1>BINOMO SIGNAL</h1>
    <p class="subtitle">Made by Elite Trader</p>

    <div class="container">
        <div class="label">PLATFORM:</div>
        <select id="platform">
            <option>EUR/USD</option>
            <option>Crypto IDX</option>
            <option>EUR/CAD</option>
        </select>

        <div class="label">MIN ACCURACY:</div>
        <select id="min-accuracy">
            <option>70%</option>
            <option>75%</option>
            <option>80%</option>
        </select>

        <div class="label">MAX ACCURACY:</div>
        <select id="max-accuracy">
            <option>85%</option>
            <option>90%</option>
            <option>95%</option>
            <option>100%</option>
        </select>

        <div class="label">EXPIRATION TIME:</div>
        <select id="expiration">
            <option>1min</option>
            <option>5min</option>
            <option>10min</option>
            <option>30min</option>
        </select>

        <div class="label">STRATEGY:</div>
        <select id="strategy">
            <option>Breakout Trading</option>
            <option>Momentum Trading</option>
            <option>Growth Trading</option>
        </select>

        <div class="label">GROWTH OF INVESTMENT:</div>
        <select id="investment">
            <option>10%</option>
            <option>20%</option>
            <option>30%</option>
            <option>40%</option>
            <option>50%</option>
            <option>60%</option>
            <option>70%</option>
            <option>80%</option>
            <option>90%</option>
            <option>100%</option>
        </select>

        <button class="generate-btn" onclick="askForKey()">GENERATE SIGNAL</button>

        <div id="signal-container"></div>
    </div>

    <script>
        function askForKey() {
            let key = prompt("Enter the key to generate a signal:");
            if (key === "ELITE999") {
                generateSignals();
            } else {alert("Incorrect key! Please enter the correct key.");
            }
        }

        function generateSignals() {
            const platform = document.getElementById("platform").value;
            const minAccuracy = document.getElementById("min-accuracy").value;
            const maxAccuracy = document.getElementById("max-accuracy").value;
            const expiration = document.getElementById("expiration").value;
            const strategy = document.getElementById("strategy").value;
            const investment = document.getElementById("investment").value;

            let signalContainer = document.getElementById("signal-container");
            signalContainer.innerHTML = ""; // Clear previous signals

            let currentTime = new Date(); // Get current time

            for (let i = 0; i < 5; i++) {
                let signalType = Math.random() > 0.5 ? "BUY" : "SELL"; 

                // Add 2-3 minutes gap for each signal
                let futureTime = new Date(currentTime.getTime() + (Math.floor(Math.random() * 2) + 2 + i * 2) * 60000);
                let formattedTime = futureTime.toLocaleTimeString("en-IN", { hour: '2-digit', minute: '2-digit', second: '2-digit', hour12: true, timeZone: "Asia/Kolkata" });

                let signalHTML = `
                    <div class="signal-box">
                        <p>Signal ${i + 1}</p>
                        <p>Platform: <strong>${platform}</strong></p>
                        <p>Signal: <strong>${signalType}</strong></p>
                        <p>Accuracy: <strong>${minAccuracy} - ${maxAccuracy}</strong></p>
                        <p>Expiration: <strong>${expiration}</strong></p>
                        <p>Strategy: <strong>${strategy}</strong></p>
                        <p>Investment Growth: <strong>${investment}</strong></p>
                        <p>Time: <strong>${formattedTime} IST</strong></p>
                    </div>
                `;

                signalContainer.innerHTML += signalHTML;
            }
        }
    </script>

</body>
</html>
