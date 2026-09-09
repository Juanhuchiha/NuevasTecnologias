Instructivo para ejecutar la API de productos

Este instructivo explica paso a paso cómo ejecutar el proyecto de la API de productos en un computador diferente al utilizado para desarrollar el código.

1. Encender el computador
Presionar el botón de encendido del computador.
Esperar hasta que el computador termine de iniciar.
Ingresar la contraseña o PIN si el computador lo solicita.
Esperar hasta que aparezca el escritorio de Windows.
2. Tener los archivos del proyecto

Antes de comenzar, se debe tener en el computador la carpeta que contiene el código del proyecto.

La carpeta debe contener como mínimo el siguiente archivo:

app.py

Por ejemplo, se puede guardar la carpeta en el escritorio.

La estructura debe verse de la siguiente manera:

API_Productos
└── app.py
3. Abrir Visual Studio Code
Hacer clic en el botón Inicio de Windows.
Escribir en el buscador:
Visual Studio Code
Hacer clic en la aplicación Visual Studio Code.
Esperar hasta que el programa se abra completamente.
4. Abrir la carpeta del proyecto
En Visual Studio Code, dirigirse a la parte superior izquierda.
Hacer clic en File o Archivo.
Seleccionar Open Folder... o Abrir carpeta....
Se abrirá una ventana del explorador de archivos.
Buscar la ubicación donde se guardó la carpeta del proyecto.
Seleccionar la carpeta:
API_Productos
Hacer clic en Seleccionar carpeta.
Esperar a que Visual Studio Code cargue el proyecto.

En la parte izquierda de Visual Studio Code debe aparecer el archivo:

app.py
5. Abrir el código
En el panel izquierdo de Visual Studio Code buscar el archivo app.py.
Hacer doble clic sobre app.py.
El código aparecerá en la parte central del programa.
Verificar que el archivo contenga el código de la API.

El código debe tener correctamente estas dos partes:

app = Flask(__name__)

y al final:

if __name__ == '__main__':
    app.run(debug=True)

Es importante que __name__ y __main__ tengan dos guiones bajos antes y después.

6. Abrir la terminal

Para ejecutar el código se necesita utilizar la terminal de Visual Studio Code.

En la parte superior de Visual Studio Code hacer clic en Terminal.
Seleccionar New Terminal o Nueva terminal.
En la parte inferior de la pantalla aparecerá la terminal.

La terminal debe encontrarse ubicada dentro de la carpeta del proyecto.

Por ejemplo:

C:\Users\Usuario\Desktop\API_Productos>
7. Comprobar que Python esté instalado

En la terminal escribir:

python --version

Presionar Enter.

Debe aparecer algo parecido a:

Python 3.13.5

La versión puede ser diferente.

Si el comando anterior no funciona, escribir:

py --version

y presionar Enter.

Si ninguno de los dos comandos muestra una versión de Python, significa que Python no está instalado correctamente y se debe instalar antes de continuar.

8. Instalar Python si no está instalado

Si el computador no tiene Python instalado:

Abrir un navegador de Internet.
Buscar la página oficial de Python.
Descargar e instalar Python para Windows.
Durante la instalación, activar la opción:
Add Python to PATH
Continuar con la instalación.
Esperar hasta que finalice.
Cerrar y volver a abrir Visual Studio Code.
Abrir nuevamente la terminal.
Ejecutar:
python --version
Comprobar que aparezca la versión de Python.
9. Instalar Flask

Una vez comprobado que Python está instalado, se debe instalar Flask.

Hacer clic dentro de la terminal de Visual Studio Code.
Escribir:
pip install flask o python -m pip install flask
Presionar Enter.
Esperar mientras Flask se descarga e instala.
Cuando termine el proceso, se puede continuar con el siguiente paso.

Si el computador ya tenía Flask instalado, puede aparecer un mensaje indicando que el paquete ya está instalado.

10. Ejecutar el código

Una vez instalado Flask:

Verificar que la terminal se encuentre dentro de la carpeta donde está app.py.
Escribir:
python app.py
Presionar Enter.
Esperar unos segundos.

Si todo funciona correctamente, aparecerá un mensaje similar a:

* Serving Flask app 'app'
* Debug mode: on
* Running on http://127.0.0.1:5000

Esto significa que la aplicación se está ejecutando correctamente.

11. No cerrar la terminal

Mientras se esté utilizando la aplicación:

No se debe cerrar Visual Studio Code ni detener la terminal donde está ejecutándose Flask.

El servidor debe permanecer activo para poder acceder a la API.

Si aparece:

Running on http://127.0.0.1:5000

la aplicación está lista para utilizarse.

12. Comprobar que la aplicación funciona

Para comprobar que el código funciona correctamente:

Abrir un navegador como Google Chrome, Microsoft Edge u Opera.
Hacer clic en la barra de direcciones.
Escribir:
http://127.0.0.1:5000/
Presionar Enter.

Debe aparecer el siguiente mensaje:

Welcome to the Flask API!

Si aparece este mensaje, significa que el servidor Flask está funcionando correctamente.

13. Comprobar la API de productos

Para comprobar que la API está funcionando, abrir en el navegador:

http://127.0.0.1:5000/api/productos

Al presionar Enter, deben aparecer los productos registrados:

[
    {
        "id": 1,
        "nombre": "Laptop",
        "precio": 1200
    },
    {
        "id": 2,
        "nombre": "Mouse",
        "precio": 25
    },
    {
        "id": 3,
        "nombre": "Teclado",
        "precio": 75
    }
]

Si aparecen estos productos, la API se encuentra funcionando correctamente.

14. Utilizar la API

Una vez ejecutado el proyecto, la dirección principal de la API es:

http://127.0.0.1:5000

Las diferentes operaciones disponibles son:

Consultar todos los productos
GET
http://127.0.0.1:5000/api/productos
Consultar un producto específico

Por ejemplo, para consultar el producto con ID 1:

GET
http://127.0.0.1:5000/api/productos/1
Crear un producto
POST
http://127.0.0.1:5000/api/productos

El cuerpo de la solicitud debe enviarse en formato JSON.

Ejemplo:

{
    "id": 4,
    "nombre": "Monitor",
    "precio": 350
}
Modificar un producto

Por ejemplo, para modificar el producto con ID 4:

PUT
http://127.0.0.1:5000/api/productos/4

Ejemplo de información enviada:

{
    "nombre": "Monitor Gamer",
    "precio": 450
}
Eliminar un producto

Por ejemplo, para eliminar el producto con ID 4:

DELETE
http://127.0.0.1:5000/api/productos/4
15. Finalizar la ejecución

Cuando se hayan terminado las pruebas:

Regresar a Visual Studio Code.
Hacer clic en la terminal donde está ejecutándose Flask.
Presionar:
Ctrl + C
El servidor se detendrá.

Para volver a ejecutar el proyecto posteriormente, solamente se debe abrir nuevamente la carpeta del proyecto en Visual Studio Code y ejecutar:

python app.py
