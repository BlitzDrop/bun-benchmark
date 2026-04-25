# Benchmark de Rendimiento: Node.js vs Bun

Este documento detalla los pasos para realizar una prueba de carga en una aplicación Express utilizando la herramienta `oha`. El objetivo es comparar el rendimiento del servidor ejecutándose en Node.js frente a Bun.

## Requisitos

Para ejecutar esta prueba, asegúrate de tener instalados:

- Node.js
- Bun
- oha

## Configuración Inicial

Antes de ejecutar las pruebas, instala las dependencias necesarias:

```bash
npm install
```

## Ejecución de Pruebas

A continuación se detalla cómo ejecutar el servidor y la prueba de estrés de 500,000 peticiones para cada entorno. 

### 1. Prueba con Node.js

Paso 1: Inicia el servidor utilizando Node.js en una terminal.

```bash
node express.mjs
```

Paso 2: Abre una segunda terminal y lanza la prueba de carga con `oha`.

```bash
oha http://localhost:3000 -n 500000 -H "Accept-Encoding: identity"
```

### 2. Prueba con Bun

Paso 1: Inicia el servidor utilizando Bun en una terminal.

```bash
bun run express.mjs
```

Paso 2: En la segunda terminal, ejecuta exactamente la misma prueba de carga.

```bash
oha http://localhost:3000 -n 500000 -H "Accept-Encoding: identity"
```
