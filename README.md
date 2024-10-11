# latihan1

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css" />
    <title>IoT Temperature Controller</title>
</head>
<body>
    <header>
        <h1 class="title">Web Monitoring IoT</h1>
        <h2 class="welcome">Selamat Datang!</h2>
    </header>
    <section class="section-card">
        <!-- Current Temperature Card -->
        <div class="card card-1">
            <div class="card-header">
                <h3>Current Temperature</h3>
                <div class="gauge__value">22.4°C</div>
            </div>
            <div class="gauge-container">
                <div class="gauge">
                    <div class="gauge__fill" style="width: 22.4%; background-color: #2196F3;"></div>
                </div>
            </div>
        </div>
        <!-- Temperature Setpoint Card -->
        <div class="card card-2">
            <div class="card-header">
                <h3>sensor suhu</h3>
                <div class="gauge__value">21.2°C</div>
            </div>
            <div class="gauge-container">
                <div class="gauge">
                    <div class="gauge__fill" style="width: 21.2%; background-color: #673AB7;"></div>
                </div>
            </div>
        </div>
        <!-- Humidity Value Card -->
        <div class="card card-3">
            <div class="card-header">
                <h3>suhu thermal themperature</h3>
                <div class="gauge__value">65%</div>
            </div>
            <div class="gauge-container">
                <div class="gauge">
                    <div class="gauge__fill" style="width: 65%; background-color: #FF9800;"></div>
                </div>
            </div>
        </div>
        <!-- Heart Rate Monitor Card -->
        <div class="card card-4">
            <div class="card-header">
                <h3>detak jantung</h3>
                <div class="gauge__value"><i class="fas fa-heart" style="color: red;"></i> 72 bpm</div>
            </div>
            <div class="gauge-container">
                <div class="gauge">
                    <div class="gauge__fill" style="width: 72%; background-color: red;"></div>
                </div>
            </div>
        </div>
        <!-- Automatic Mode Toggle -->
        <div class="card card-5">
            <h3>Automatic Mode</h3>
            <button class="bn-toggle">OFF</button>
        </div>
        <!-- Set Temperature and Humidity -->
        <div class="card card-6">
            <h3>Set Temperature & Humidity</h3>
            <label for="set-temp">Set Temperature</label>
            <input type="range" id="set-temp" min="16" max="30" value="22" />
            <label for="set-humidity">Set Humidity</label>
            <input type="range" id="set-humidity" min="30" max="100" value="65" />
            <div class="button-group">
                <button class="btn">ON</button>
                <button class="btn">OFF</button>
            </div>
        </div>
        <!-- 4 Button Control Section -->
        <div class="card card-7">
            <h3>Relay Control</h3>
            <div class="button-group-grid">
                <button class="button">saklar1</button>
                <button class="button">saklar2</button>
                <button class="button">saklar 3</button>
                <button class="button">saklar 4</button>
            </div>
        </div>
        <!-- Web Visitor Graph Card -->
        <div class="card card-8">
            <h3>Web Visitor Statistics</h3>
            <canvas id="visitorChart"></canvas>
        </div>
    </section>
    <!-- Smart Home Device Icons -->
    <div class="icon-container">
        <i class="fas fa-lightbulb" title="Smart Light"></i>
        <i class="fas fa-fan" title="Smart Fan"></i>
        <i class="fas fa-tv" title="Smart TV"></i>
        <i class="fas fa-thermometer-half" title="Smart Thermostat"></i>
        <i class="fas fa-door-open" title="Smart Door"></i>
        <i class="fas fa-lock" title="Smart Lock"></i>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        // Data untuk pengunjung dan detak jantung
        const ctx = document.getElementById('visitorChart').getContext('2d');
        const visitorChart = new Chart(ctx, {
            type: 'line',
            data: {
                labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul'], // Label untuk waktu, bisa disesuaikan
                datasets: [
                    {
                        label: 'Visitors', // Label untuk pengunjung
                        data: [50, 100, 150, 200, 250, 300, 350], // Data pengunjung
                        backgroundColor: 'rgba(33, 150, 243, 0.2)',
                        borderColor: 'rgba(33, 150, 243, 1)',
                        borderWidth: 2,
                        fill: true,
                    },
                    {
                        label: 'Heart Rate (bpm)', // Label untuk detak jantung
                        data: [72, 75, 70, 68, 80, 74, 78], // Data detak jantung
                        backgroundColor: 'rgba(255, 99, 132, 0.2)',
                        borderColor: 'rgba(255, 99, 132, 1)',
                        borderWidth: 2,
                        fill: true,
                    }
                ]
            },
            options: {
                responsive: true,
                scales: {
                    y: {
                        beginAtZero: true,
                        title: {
                            display: true,
                            text: 'Values'
                        }
                    },
                    x: {
                        title: {
                            display: true,
                            text: 'Months'
                        }
                    }
                }
            }
        });
    </script>
    
</body>
</html>























* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: linear-gradient(to right, #e0f7fa, #80deea);
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.title {
    text-align: center;
    font-size: 32px;
    font-weight: bold;
    margin: 20px 0;
    color: #004d40;
}

.welcome {
    font-size: 24px;
    color: #00796b;
    margin-bottom: 20px;
}

.section-card {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 20px;
    width: 80%;
    max-width: 1200px;
}

.card {
    background: white;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
    padding: 20px;
    text-align: center;
    transition: transform 0.2s;
}

.card:hover {
    transform: scale(1.05);
}

.card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.gauge-container {
    margin-top: 10px;
}

.gauge {
    height: 15px;
    border-radius: 10px;
    background: #e0e0e0;
    position: relative;
}

.gauge__fill {
    height: 100%;
    border-radius: 10px;
}

.gauge__value {
    font-size: 18px;
    font-weight: bold;
}

.button-toggle {
    background-color: #ff4081;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 10px 15px;
    cursor: pointer;
    font-size: 16px;
}

.button-toggle:hover {
    background-color: #f50057;
}

.button-group, .button-group-grid {
    display: flex;
    justify-content: space-around;
    margin-top: 15px;
}

.button-group-grid {
    flex-wrap: wrap;
}

.button {
    background-color: #2196F3;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 10px 15px;
    cursor: pointer;
    font-size: 16px;
    flex: 1;
    margin: 5px;
}

.buttonn:hover {
    background-color: #1976D2;
}

/* Web Visitor Graph */
.card-8 {
    grid-column: span 2; /* Make the graph card span 2 columns */
}

#visitorChart {
    width: 100%;
    height: 200px;
}

/* Smart Home Icons */
.icon-container {
    margin-top: 30px;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
}

.icon-container i {
    font-size: 40px;
    color: #00796b;
    transition: color 0.3s;
}

.icon-container i:hover {
    color: #004d40;
}
