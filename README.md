# Actividades-del-DOM.js
Actividades del DOM resueltas
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lista Interactiva</title>
  <style>
    ul {
      list-style-type: none;
      padding: 0;
    }
    li {
      margin: 5px 0;
    }
    .boton-eliminar {
      margin-left: 10px;
      color: red;
      cursor: pointer;
    }
    li:hover {
      background-color: #f0f0f0;
    }
    #parrafo {
      padding: 10px;
    }
  </style>
</head>
<body>
  <h1>Lista Interactiva</h1>
  <input type="text" id="nuevoElemento" placeholder="Escribe algo...">
  <button onclick="agregarElemento()">Agregar</button>
  <ul id="lista"></ul>

  <h2>Párrafo con botón para cambiar color</h2>
  <p id="parrafo">Este es un párrafo cuyo color de fondo puede cambiar.</p>
  <button onclick="cambiarColorParrafo()">Cambiar Color</button>

  <script>
    function agregarElemento() {
      let input = document.getElementById("nuevoElemento");
      let texto = input.value.trim();
      if (texto !== "") {
        let li = document.createElement("li");
        li.textContent = texto;

        // Botón para eliminar el elemento
        let botonEliminar = document.createElement("span");
        botonEliminar.textContent = " Eliminar";
        botonEliminar.className = "boton-eliminar";
        botonEliminar.onclick = function() {
          this.parentElement.remove();
        };

        li.appendChild(botonEliminar);
        document.getElementById("lista").appendChild(li);
        input.value = "";
      }
    }

    function cambiarColorParrafo() {
      let parrafo = document.getElementById("parrafo");
      parrafo.style.backgroundColor = generarColorAleatorio();
    }

    function generarColorAleatorio() {
      let letras = "0123456789ABCDEF";
      let color = "#";
      for (let i = 0; i < 6; i++) {
        color += letras[Math.floor(Math.random() * 16)];
      }
      return color;
    }
  </script>
</body>
</html>

