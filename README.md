- 👋 Hi, I’m @maya4444
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
maya4444/maya4444 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mercosur: La Ruta de la Integración</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Mercosur: La Ruta de la Integración</h1>
    <p>Aprende sobre la cooperación económica y política en el Mercosur mientras juegas.</p>
  </header>
  
  <section class="intro">
    <h2>¿Cómo se juega?</h2>
    <p>En este juego representas a un país del Mercosur. ¡El objetivo es hacer crecer tu economía, mejorar las relaciones diplomáticas y mantener la estabilidad!</p>
    <a href="game.html" class="btn">¡Comienza a Jugar!</a>
  </section>

  <footer>
    <p>&copy; 2024 Mercosur: La Ruta de la Integración. Todos los derechos reservados.</p>
  </footer>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f9;
  margin: 0;
  padding: 0;
}

header {
  background-color: #4CAF50;
  color: white;
  text-align: center;
  padding: 20px;
}

h1 {
  margin: 0;
}

.intro {
  padding: 20px;
  text-align: center;
}

.btn {
  display: inline-block;
  margin-top: 20px;
  padding: 15px 30px;
  background-color: #007BFF;
  color: white;
  text-decoration: none;
  border-radius: 5px;
}

footer {
  text-align: center;
  padding: 10px;
  background-color: #333;
  color: white;
}<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Juego: Mercosur</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Juego: Mercosur</h1>
    <p>¡Haz crecer la economía de tu país y mantén la estabilidad!</p>
  </header>

  <section id="game-board">
    <h2>Tu país: <span id="country-name">Argentina</span></h2>
    <div id="status">
      <p>PIB: <span id="pib">1000</span></p>
      <p>Estabilidad: <span id="stability">70%</span></p>
      <p>Relaciones Diplomáticas: <span id="relations">80%</span></p>
    </div>

    <div id="actions">
      <button id="internal-policy">Política Interna</button>
      <button id="external-policy">Política Externa</button>
      <button id="event">Evento Internacional</button>
      <button id="update-status">Actualizar Estado</button>
    </div>

    <div id="game-log">
      <h3>Registro de Acciones:</h3>
      <ul id="log-list">
        <!-- Aquí se agregarán las acciones tomadas -->
      </ul>
    </div>
  </section>

  <footer>
    <p>&copy; 2024 Mercosur: La Ruta de la Integración. Todos los derechos reservados.</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
document.addEventListener('DOMContentLoaded', () => {
  const countryName = document.getElementById('country-name');
  const pib = document.getElementById('pib');
  const stability = document.getElementById('stability');
  const relations = document.getElementById('relations');
  const logList = document.getElementById('log-list');

  let country = {
    name: 'Argentina',
    pib: 1000,
    stability: 70,
    relations: 80
  };

  function updateGameStatus() {
    pib.textContent = country.pib;
    stability.textContent = ${country.stability}%;
    relations.textContent = ${country.relations}%;
  }

  function logAction(action) {
    const li = document.createElement('li');
    li.textContent = action;
    logList.appendChild(li);
  }

  // Botones de acción
  document.getElementById('internal-policy').addEventListener('click', () => {
    country.pib += 50;
    country.stability += 5;
    logAction('Se ha implementado una política interna que mejora la economía y la estabilidad.');
    updateGameStatus();
  });

  document.getElementById('external-policy').addEventListener('click', () => {
    country.relations += 10;
    logAction('Se ha firmado un acuerdo comercial con otro país del Mercosur.');
    updateGameStatus();
  });

  document.getElementById('event').addEventListener('click', () => {
    const randomEvent = Math.random();
    if (randomEvent < 0.5) {
      country.pib -= 100;
      logAction('Crisis económica mundial afecta el PIB.');
    } else {
      country.stability += 10;
      logAction('Evento internacional mejora la estabilidad política.');
    }
    updateGameStatus();
  });

  document.getElementById('update-status').addEventListener('click', () => {
    updateGameStatus();
    logAction('Estado actualizado.');
  });
});
