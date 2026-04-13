# Ejercicio 1 – Script de Pruebas de Carga

## 1. Prerrequisitos

Para ejecutar este proyecto se requiere:

* Sistema Operativo: Windows 10 o superior
* Java JDK 8 o superior (configurado en variables de entorno)
* Apache JMeter versión 5.6.3 o superior

---

## 2. Estructura del Proyecto

* `Ejercicio 1 – Script de Pruebas de Carga.jmx` → Script de prueba en JMeter
* `credenciales.csv` → Datos de entrada parametrizados
* `resultados.jtl` → Resultados de ejecución
* `README.md` → Instrucciones del proyecto
* `conclusiones.txt` → Hallazgos y conclusiones

---

## 3. Configuración de la Prueba

La prueba consiste en realizar una carga sobre el servicio de login:

* Endpoint: https://fakestoreapi.com/auth/login
* Método: POST
* Tipo de contenido: application/json

Se utilizó parametrización mediante archivo CSV con usuarios y contraseñas.

---

## 4. Ejecución de la Prueba

### Paso 1: Abrir JMeter

Ejecutar el archivo:

```bash
jmeter.bat
```

---

### Paso 2: Cargar el script

* Ir a File → Open
* Seleccionar el archivo `Ejercicio 1 – Script de Pruebas de Carga .jmx`

---

### Paso 3: Ejecutar la prueba

* Presionar el botón ▶ (Start)

---

### Paso 4: Ejecución en modo no gráfico (opcional)

```bash
jmeter -n -t test.jmx -l resultados.jtl
```

---

## 5. Configuración de Carga

* Número de hilos: 20
* Ramp-up: 10 segundos
* Duración: 60 segundos
* Throughput: 1200 muestras/minuto (equivalente a 20 TPS)

---

## 6. Validaciones Implementadas

* Response Assertion → Código HTTP 200
* Duration Assertion → Tiempo máximo 1500 ms

---

## 7. Métricas Evaluadas

* Throughput (TPS)
* Tiempo de respuesta promedio
* Porcentaje de error

---

## 8. Información Adicional

Durante la ejecución se detectó un problema de disponibilidad en el endpoint proporcionado (error SSL 526), lo cual puede afectar los resultados de la prueba.

En un escenario real, se recomienda validar la disponibilidad del servicio antes de ejecutar pruebas de carga.
