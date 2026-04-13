# Ejercicio 1 – Script de Pruebas de Carga

## 1. Prerrequisitos

Para ejecutar este proyecto se requiere:

* Sistema Operativo: Windows 10 o superior
* Java JDK 8 o superior (configurado en variables de entorno)
* Apache JMeter 5.6.3 o superior

---

## 2. Estructura del Proyecto

* `test.jmx` → Script de prueba en JMeter
* `credenciales.csv` → Datos de entrada
* `resultados.jtl` → Resultados de ejecución
* `README.md` → Instrucciones
* `conclusiones.txt` → Hallazgos

---

## 3. Descripción de la Prueba

Se ejecuta una prueba de carga sobre el servicio:

* Endpoint: https://fakestoreapi.com/auth/login
* Método: POST
* Content-Type: application/json

Se simulan múltiples usuarios mediante archivo CSV.

---

## 4. Configuración del Escenario

* Número de hilos: 20
* Ramp-up: 10 segundos
* Duración: 60 segundos
* Throughput: 1200 muestras/minuto (~20 TPS)

---

## 5. Validaciones

* Código de respuesta HTTP = 200
* Tiempo máximo de respuesta ≤ 1500 ms
* Tasa de error < 3%

---

## 6. Ejecución

### Modo gráfico:

1. Abrir JMeter
2. Cargar el archivo `.jmx`
3. Ejecutar la prueba

### Modo no gráfico:

```
jmeter -n -t test.jmx -l resultados.jtl
```

---

## 7. Resultados Obtenidos

* Throughput: 18.6 TPS
* Tiempo promedio: 633 ms
* Error: 0.62%

---

## 8. Conclusión General

El sistema responde correctamente bajo carga, manteniendo tiempos de respuesta aceptables y una baja tasa de error.
