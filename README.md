# analisis-gobernanza-textil
"Análisis de gobernanza e integración vertical en la industria textil"
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Industria Textil en Chile - Integración Vertical</title>

  <style>
    body {
      font-family: Arial;
      background: #f5f5f5;
      margin: 40px;
    }

    .box {
      background: white;
      padding: 25px;
      border-radius: 10px;
      margin-bottom: 20px;
    }

    h1, h2 {
      color: #222;
    }

    input {
      width: 100%;
      margin-top: 10px;
    }

    .resultado {
      margin-top: 15px;
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="box">
  <h1>Industria Textil en Chile</h1>

  <h2>1. Dimensión Teórica</h2>
  <p>
    Según Ronald Coase (1937), las empresas existen porque utilizar el mercado implica
    costos de transacción, como la búsqueda de proveedores, negociación de contratos
    y control del cumplimiento. En la industria textil chilena, estos costos son altos
    debido a la dependencia de importaciones y múltiples intermediarios.
  </p>

  <p>
    La empresa surge como una alternativa al mercado, coordinando internamente mediante
    jerarquías. Sin embargo, a mayor integración vertical, aumentan los costos de
    coordinación interna, como la gestión, supervisión y burocracia.
  </p>

  <p>
    Por lo tanto, el tamaño óptimo de la empresa se determina cuando el costo total
    (transacción + coordinación) es mínimo.
  </p>
</div>

<div class="box">
  <h2>2. Aplicación Práctica: Industria Textil Chilena</h2>

  <p>
    La industria textil en Chile se caracteriza por una alta dependencia de importaciones,
    especialmente desde Asia, lo que implica elevados costos de transacción asociados a
    logística, negociación y riesgo de incumplimiento.
  </p>

  <p>
    Algunas empresas han optado por integrar verticalmente ciertas actividades, como
    almacenamiento, distribución o marcas propias, con el objetivo de reducir estos costos.
  </p>

  <p>
    Sin embargo, una integración excesiva puede generar altos costos de coordinación,
    como mayor complejidad organizacional y aumento de la burocracia interna.
  </p>
</div>

<div class="box">
  <h2>3. Modelo Interactivo: Nivel Óptimo de Integración</h2>

  <label>Grado de integración vertical:</label>
  <input type="range" min="0" max="100" value="40" id="slider">

  <div class="resultado" id="resultado"></div>
</div>

<script>
  const slider = document.getElementById("slider");
  const resultado = document.getElementById("resultado");

  function calcular(valor) {
    valor = parseInt(valor);

    // modelo aplicado a industria textil
    let costoTransaccion = 120 - valor * 1.2; 
    let costoCoordinacion = valor * 1.5; 

    let total = costoTransaccion + costoCoordinacion;

    let mensaje = "";

    if (total < 140 && total > 120) {
      mensaje = "✔ Nivel cercano al óptimo de integración";
    } else if (valor < 30) {
      mensaje = "⚠ Alta dependencia del mercado (importaciones y proveedores externos)";
    } else if (valor > 70) {
      mensaje = "⚠ Exceso de integración (altos costos internos de gestión)";
    }

    resultado.innerHTML = `
      Integración: ${valor}% <br>
      Costo de Transacción: ${costoTransaccion.toFixed(1)} <br>
      Costo de Coordinación: ${costoCoordinacion.toFixed(1)} <br>
      Costo Total: ${total.toFixed(1)} <br><br>
      ${mensaje}
    `;
  }

  slider.addEventListener("input", () => {
    calcular(slider.value);
  });

  calcular(40);
</script>


</body>
</html>
