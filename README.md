# Jarvis flotante — stack recomendado (MVP)

Este documento resume una arquitectura práctica para empezar un asistente de escritorio “tipo Jarvis flotante” sin sobrecomplicar el inicio.

## Estado actual: qué ya está hecho y qué falta

### ✅ Hecho hasta ahora
- Se definió la arquitectura base (UI flotante → shell de escritorio → backend Python → API IA → automatización).
- Se eligió un stack recomendado para arrancar rápido:
  - Frontend: React + Tailwind
  - Desktop: Electron (opción más simple para MVP)
  - Backend: Python + FastAPI
  - IA: OpenAI API
- Se definió un roadmap MVP por semanas (4 semanas).
- Se documentó el alcance inicial para evitar sobreingeniería.

### ⏳ Falta por implementar (código)
1. Inicializar proyecto de escritorio (Electron + React + Tailwind).
2. Crear ventana flotante siempre visible (always-on-top) con estilo básico.
3. Añadir input de texto y vista de conversación.
4. Levantar backend con FastAPI y endpoint `/chat`.
5. Conectar backend con OpenAI API (variables de entorno + llamada mínima).
6. Conectar frontend ↔ backend para enviar/recibir mensajes.
7. Añadir comandos locales simples (ejemplo: abrir YouTube / abrir app).
8. Añadir voz (STT/TTS) como fase opcional.

### 🎯 Definición de “MVP listo”
Se considera MVP cuando:
- puedes escribir o hablar una orden,
- el asistente responde,
- y ejecuta al menos 2–3 acciones locales útiles (abrir navegador, abrir app, búsqueda rápida).

## Lo necesario

1. **Editor de código**
   - Visual Studio Code
   - Extensiones: Python, Tailwind, React, Codex/Copilot

2. **IA para programar**
   - OpenAI Codex CLI (edición de archivos, generación de código, ayuda con arquitectura, automatización)
   - Integración opcional con VS Code

3. **Frontend flotante**
   - **Camino A (fácil): Electron + React + Tailwind**
   - **Camino B (moderno): Tauri + React + Tailwind**

4. **Backend**
   - Python (comandos, automatización, IA, voz, control del sistema)

5. **API de IA**
   - OpenAI API Platform

6. **Voz (opcional)**
   - Speech-to-text: Whisper
   - Text-to-speech: ElevenLabs o TTS local

7. **Automatización del sistema**
   - `pyautogui`, `playwright`, `subprocess`

## Flujo de arquitectura

```text
Floating UI (React)
        ↓
Desktop Shell (Electron/Tauri)
        ↓
Python Backend
        ↓
OpenAI API
        ↓
Automation Tools
```

## Flujo de ejemplo

Usuario: “abre YouTube”

1. La app escucha voz o texto.
2. Convierte voz a texto (si aplica).
3. La IA interpreta intención.
4. El backend ejecuta una acción (`open_browser("youtube.com")`).
5. La app responde: “Listo.”

## Plan MVP en 4 semanas

- **Semana 1**: ventana flotante + input de texto + chat básico.
- **Semana 2**: conexión a OpenAI API + respuestas IA.
- **Semana 3**: comandos simples (abrir apps, acciones básicas).
- **Semana 4**: voz, animaciones, transparencia.

## Stack recomendado

- **Frontend**: React + Tailwind
- **Desktop**: Electron
- **Backend**: Python + FastAPI
- **IA**: OpenAI API
- **Editor**: VS Code + Codex

## Enfoque para no bloquear el proyecto

Evitar al inicio:
- memoria “infinita”,
- agentes totalmente autónomos,
- control total del sistema,
- visión por computadora compleja.

Objetivo inicial:

> “Asistente flotante que responde, abre apps, busca cosas y usa voz.”

Eso ya es útil, demostrable y alcanzable como primera versión.
