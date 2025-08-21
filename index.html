<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>📡 Telemetría CanSat</title>
<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-database-compat.js"></script>
<style>
    body { font-family: Arial, sans-serif; margin: 20px; background: #f4f4f4; }
    h1 { text-align: center; color: #333; }
    #graphs { display: grid; grid-template-columns: 1fr; gap: 20px; }
    .graph-container { background: #fff; padding: 15px; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
</style>
</head>
<body>

<h1>📡 Telemetría CanSat en Tiempo Real</h1>
<div id="graphs">
    <div id="tempGraph" class="graph-container"></div>
    <div id="humGraph" class="graph-container"></div>
    <div id="presGraph" class="graph-container"></div>
    <div id="altGraph" class="graph-container"></div>
</div>

<script>
// Configuración Firebase
const firebaseConfig = {
    databaseURL: "https://cansat-web-default-rtdb.europe-west1.firebasedatabase.app"
};
firebase.initializeApp(firebaseConfig);
const dbRef = firebase.database().ref('canSatData');

let timestamps = [], temps = [], hums = [], press = [], alts = [];

function updateGraphs() {
    Plotly.newPlot('tempGraph', [{ x: timestamps, y: temps, type: 'scatter', mode: 'lines+markers', name: 'Temp (°C)', line: {color: '#FF5733'} }], { title: 'Temperatura (°C)' });
    Plotly.newPlot('humGraph', [{ x: timestamps, y: hums, type: 'scatter', mode: 'lines+markers', name: 'Hum (%)', line: {color: '#33A1FF'} }], { title: 'Humedad (%)' });
    Plotly.newPlot('presGraph', [{ x: timestamps, y: press, type: 'scatter', mode: 'lines+markers', name: 'Presión (hPa)', line: {color: '#33FF57'} }], { title: 'Presión (hPa)' });
    Plotly.newPlot('altGraph', [{ x: timestamps, y: alts, type: 'scatter', mode: 'lines+markers', name: 'Altitud (m)', line: {color: '#FFC300'} }], { title: 'Altitud (m)' });
}

// Leer datos de Firebase
dbRef.limitToLast(100).on('value', snapshot => {
    timestamps = []; temps = []; hums = []; press = []; alts = [];
    snapshot.forEach(child => {
        const data = child.val();
        timestamps.push(new Date(data.time).toLocaleTimeString());
        temps.push(data.temp);
        hums.push(data.hum);
        press.push(data.pres);
        alts.push(data.alt);
    });
    updateGraphs();
});

// Actualizar automáticamente cada minuto
setInterval(() => {
    dbRef.limitToLast(100).once('value', snapshot => {
        timestamps = []; temps = []; hums = []; press = []; alts = [];
        snapshot.forEach(child => {
            const data = child.val();
            timestamps.push(new Date(data.time).toLocaleTimeString());
            temps.push(data.temp);
            hums.push(data.hum);
            press.push(data.pres);
            alts.push(data.alt);
        });
        updateGraphs();
    });
}, 60000);

</script>
</body>
</html>
