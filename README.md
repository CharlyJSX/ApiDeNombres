# ApiDeNombres

Esta es una API para ver en que país se repite más un nombre

Vista en el navegador

![image](https://user-images.githubusercontent.com/77645310/201126189-2dc4be79-23b8-49b5-9bf6-be06486d8bfb.png)

Vista del código

![image](https://user-images.githubusercontent.com/77645310/201126953-97b4525e-5d83-44bc-8237-8b1aacf91e5f.png)

```python
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>API de nombres</title>

    <script type="text/javascript">
      async function traerPais() {
        const respuesta = await fetch(
          "https://api.nationalize.io/?name=mancia"
        );
        if (!respuesta.ok) {
          let oops = "404 no encontré nada";
          alert(oops);
          throw new Error(oops);
        }
        const nombre = respuesta.json();

        return nombre;
      }
      function mostrarNombre(n) {
        document.getElementById("mensaje").innerHTML = n.country[0].country_id;
      }

      traerPais().then(mostrarNombre);
    </script>
  </head>

  <body>
    <h1>API de nombres</h1>
    <p id="mensaje">Cargando...</p>
  </body>
</html>
```

