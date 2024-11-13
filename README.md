Politécnico Malvinas Argentinas.
---------------------------------

Tecnicatura Superior en Ciencia de Datos e Inteligencia Artificial.
-------------------------------------------------------------------

Desarrollo de Sistema de Inteligencia Artificial
----------------------------------

Profesor Lic. Martin Mirabete
-----------------------------

Autor: Cristian Roman Retamar
------------------------------


                             SISTEMA EXPERTO GRAVEDAD Y PENA DE LOS DELITOS CONTRA LA PROPIEDAD
                             ------------------------------------------------------------------

                                                            

                                                         


![Delitos Tierra del Fuego](documentacion/imagenes/delitos-imagen.jpg)







--------------------------------------------------------------------------
### README - Sistema Experto para la Clasificación de Delitos contra la Propiedad.

#### **Descripción del Proyecto**
Este sistema experto está diseñado para proporcionar una herramienta de diagnóstico y clasificación de delitos basada en reglas y árboles de decisión. Utiliza un modelo de conocimiento estructurado en torno al Código Penal de la Nación Argentina, permitiendo categorizar delitos según su gravedad las penas, uso de armas, y otros factores relevantes. Es una herramienta ideal para asistencia en tareas policiales y análisis de casos en la región de Tierra del Fuego.

---

#### **1. Objetivo de la Arquitectura del Conocimiento**
El sistema tiene como objetivo asistir en la categorización de delitos mediante un modelo automatizado que sigue el razonamiento de un experto en seguridad pública. Clasifica delitos basándose en su gravedad, tipo de violencia, uso de armas, y las penas correspondientes establecidas en el Código Penal de la Nación Argentina. Esto permite una toma de decisiones más precisa, rápida y accesible, mejorando los procesos de clasificación en situaciones complejas.

---

#### **2. Estructura de Conocimiento**

**a. Reglas**
- La base de conocimiento se organiza en reglas del tipo `IF <condición> THEN <resultado>`.
- Ejemplo:
  - **Condición:** Si el delito incluye violencia, o no y si utilizo de arma de fuego, etc...
  - **Resultado:** Clasificación como `"Robo ART..."`.

**b. Árbol de Decisión**
- Guía el sistema con preguntas específicas:
  - Ejemplo: "¿La propiedad esta violentada?"  
  - Cada respuesta conduce a una clasificación específica del delito y su Articulado el en C.P. ARG.

**c. Criterios y Factores**
- **Tipo de violencia:** Clasifica si el delito incluye violencia sobre personas o propiedades.
- **Uso de armas:** Especifica si se usó un arma (de fuego, blanca, etc.).
- **Gravedad:** Evalúa el daño causado o la intención.
- **Ubicación:** Considera áreas de alto riesgo.

**d. Estructura Jerárquica**
- Los criterios se evalúan en orden de importancia, comenzando con los factores más relevantes como la violencia, y avanzando hacia detalles como el tipo de arma, .

---

#### **3. Métodos de Inferencia**

- **Inferencia basada en reglas:** Evalúa las condiciones para determinar el diagnóstico.
- **Inferencia progresiva:** Comienza con criterios generales y avanza hacia detalles.
- **Árbol de decisión:** Simplifica el proceso de clasificación mediante nodos y respuestas.

---

#### **4. Lógica de Organización del Conocimiento**

- **Agrupación por Categorías:** Delitos se organizan en grupos amplios (Robo, Hurto, Daño, etc.).
- **Jerarquización de Decisiones:** Priorización de factores críticos.
- **Relación entre Conceptos:** Factores como violencia y uso de armas están interconectados en la base `delitos.json`.

---

#### **5. Ejemplo de Inferencia en el Sistema**

**Flujo de decisiones:**
1. Pregunta inicial: "¿La propiedad está violentada?"
   - **Sí →** "¿Hay violencia sobre personas y faltantes de bienes?"
     - **Sí →** "¿Se usó un arma?"
       - **Sí →** "¿Cuál es el tipo de arma?"
         - **Arma de fuego →** Clasificación: `"Robo Abigeato: Art. 167 ter. CP. ARG."`
         - **Arma blanca →** Clasificación: `"Robo: Art. 164 del CP. ARG."`
       - **No →** Clasificación: `"Daño: Art. 183. CP. ARG."`
   - **No →** Clasificación: `"Hurto o Usurpación según características."`

---

### Guía de Instalación y Ejecución

Guía para a configurar y ejecutar el sistema experto sobre delitos utilizando **FastAPI** para el backend y **React** para el frontend. Asegúrate de seguir cada paso con precisión.

#### Requisitos previos

- **Python** y **pip** instalados en tu sistema.
- **Node.js** y **npm** instalados.
- Editor de código como **Visual Studio Code (VSC)**.

---

### Pasos de Instalación

#### 1. Clonar el repositorio
Clona el repositorio del sistema experto a tu computadora local. Esto crea una carpeta con el proyecto.

#### 2. Configuración del Backend (FastAPI)

1. **Accede al directorio del backend** en Visual Studio Code (VSC). Asegúrate de estar en la raíz del proyecto, donde se encuentra tu archivo `main.py`.
2. Abre una terminal en VSC (Terminal > Nueva Terminal) y ejecuta el siguiente comando para iniciar el servidor backend con FastAPI:

    uvicorn main:app --reload


   Esto debería iniciar el servidor en `http://127.0.0.1:8000`. El parámetro `--reload` permite reiniciar automáticamente el servidor cada vez que realices cambios en el código.

3. Verifica en el navegador que FastAPI esté corriendo correctamente en `http://127.0.0.1:8000/docs`.

#### 3. Configuración del Frontend (React)

1. **Accede al directorio del frontend**, generalmente ubicado en `frontend/frontend` dentro de tu proyecto. Puedes hacer esto abriendo otra terminal en VSC y navegando al directorio correspondiente.

2. **Instala las dependencias de Node.js** necesarias para el proyecto. Ejecuta el siguiente comando en la terminal:

    npm install


   - Si este comando da error, es probable que **Node.js** o **npm** no estén instalados. Para instalar Node.js:
     - Descarga Node.js desde [nodejs.org](https://nodejs.org/).
     - Sigue las instrucciones de instalación y asegúrate de que Node.js esté añadido a las **variables de entorno** del sistema (Path).
   - **Verifica la instalación de Node.js** ejecutando:

     node -v
     npm -v
     

     Ambos comandos deberían mostrar un número de versión si están instalados correctamente.

3. Si **aún tienes problemas con permisos en PowerShell** al ejecutar `npm install`, ejecuta el siguiente comando en la terminal PowerShell para permitir la ejecución de scripts de manera segura:

    
    Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
    

   Luego, vuelve a ejecutar `npm install`.

4. **Inicia el servidor de desarrollo de React** en el puerto 3000 con el siguiente comando:

    npm start
    

   Esto debería iniciar el frontend en `http://localhost:3000`. Asegúrate de que este puerto no esté siendo utilizado por otra aplicación.

#### 4. Prueba de Conexión entre el Backend y el Frontend

- Asegúrate de que ambos servidores (backend en el puerto 8000 y frontend en el puerto 3000) estén ejecutándose sin errores.
- Abre `http://localhost:3000` en tu navegador para interactuar con el sistema experto a través de la interfaz del chatbot.

#### 5. Resumen de Comandos Importantes

1. Iniciar el backend de FastAPI:
   
   uvicorn main:app --reload
   

2. Instalar dependencias de React en `frontend/frontend`:
   
   npm install
   

3. Iniciar el servidor de React:
   
   npm start


Siguiendo estos pasos, deberías tener el sistema experto completamente funcional. Asegúrate de revisar cada paso para resolver posibles problemas de configuración.


### ARCHIVOS IMPORTANTES

## ARCHIVO MAIN.Py


El código crea una API REST con FastAPI para el sistema experto que clasifica delitos contra la propiedad segun su gravedad y pena. La API permite cargar una base de conocimientos (/base/cargar), iniciar una consulta (/consultar/iniciar), y procesar respuestas de usuarios (/consultar/responder). La lógica principal de inferencia reside en el motor (engine), que contiene las reglas y estructuras necesarias para el razonamiento.

* [Ver Documento](documentacion/2DA-ENTREGA-SISTEMA-EXPERTO-DELITOS.pdf)
