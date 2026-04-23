# analisis-gobernanza-textil
"Análisis de gobernanza e integración vertical en la industria textil"
YPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Capítulo 2 - Naturaleza de la Empresa</title>
  <style>
    body {
      font-family: Arial;
      background: #f0f2f5;
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
  <h1>Naturaleza y Tamaño de la Empresa</h1>

  <h2>1. Dimensión Teórica</h2>
  <p>
    Según Ronald Coase (1937), las empresas existen porque usar el mercado no es gratis.
    Existen costos de transacción como la búsqueda de información, negociación y cumplimiento
    de contratos. Frente a esto, la empresa surge como una alternativa que coordina mediante
    jerarquías en lugar de precios.
  </p>

  <p>
    Sin embargo, al crecer la empresa aparecen costos de coordinación interna como burocracia,
    supervisión y gestión. Por lo tanto, el tamaño óptimo de la empresa se determina cuando
    el costo total es mínimo.
  </p>
</div>

<div class="box">
  <h2>2. Aplicación Práctica</h2>
  <p>
    Industria: Retail (ejemplo tipo Mercado Libre).
    La empresa puede integrarse verticalmente hacia atrás (pagos) o hacia adelante (logística).
  </p>

  <p>
    A mayor integración, disminuyen los costos de transacción, pero aumentan los costos de coordinación.
  </p>
</div>

<div class="box">
  <h2>3. Modelo Interactivo</h2>

  <label>Grado de integración vertical:</label>
  <input type="range" min="0" max="100" value="50" id="slider">

  <div class="resultado" id="resultado"></div>
</div>

<script>
  const slider = document.getElementById("slider");
  const resultado = document.getElementById("resultado");

  function calcular(valor) {
    valor = parseInt(valor);

    // lógica económica real del PPT
    let costoTransaccion = 100 - valor; 
    let costoCoordinacion = valor * 1.2; 

    let total = costoTransaccion + costoCoordinacion;

    let mensaje = "";

    if (total < 110 && total > 90) {
      mensaje = "👉 Punto cercano al óptimo";
    } else if (valor < 30) {
      mensaje = "Mucho mercado (altos costos de transacción)";
    } else if (valor > 70) {
      mensaje = "Mucha jerarquía (altos costos de coordinación)";
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

  calcular(50);
</script>

</body>
</html>
<script>  const slider = document.getElementById("slider");  const resultado = document.getElementById("resultado");  function calcular(valor) {    valor = parseInt(valor);    // COSTO DE TRANSACCIÓN (disminuye pero cada vez menos)    let costoTransaccion = 120 * Math.exp(-valor / 40);    // COSTO DE COORDINACIÓN (aumenta de forma creciente - curva)    let costoCoordinacion = 0.03 * Math.pow(valor, 2);    // COSTO TOTAL    let total = costoTransaccion + costoCoordinacion;    // Detectar punto óptimo aproximado    let mensaje = "";    if (valor >= 45 && valor <= 60) {      mensaje = "⭐ Punto óptimo de integración (mínimo costo total)";    } else if (valor < 45) {      mensaje = "⚠ Alta dependencia del mercado → altos costos de transacción";    } else {      mensaje = "⚠ Exceso de integración → altos costos de coordinación";    }    resultado.innerHTML = `      Integración: ${valor}% <br>      Costo de Transacción: ${costoTransaccion.toFixed(2)} <br>      Costo de Coordinación: ${costoCoordinacion.toFixed(2)} <br>      <strong>Costo Total: ${total.toFixed(2)}</strong> <br><br>      ${mensaje}    `;  }  slider.addEventListener("input", () => {    calcular(slider.value);  });  calcular(40);</script>

