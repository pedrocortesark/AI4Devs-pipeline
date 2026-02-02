# REGISTRO DE PROMPTS UTILIZADOS
**Autor**: Pedro Cortes
**Proyecto**: LTI - Talent Tracking System
**Descripción**: Bitácora de prompts para trazabilidad del proyecto.
---

## 001 - Inicialización del Memory Bank
**Fecha:** 2026-02-02 06:08
**Prompt Original:**
> Eres una instancia experta de Gemini 3 operando como Architect Agent dentro de Google Antigravity.
> Debido a la naturaleza asíncrona y multi-agente de este IDE, tu responsabilidad es crear y mantener un Memory Bank (Estado Compartido). Esto asegura que si un agente edita el frontend y otro los tests, ambos compartan el mismo contexto sin pisarse.
>
> # Objetivo
> Generar la estructura de archivos de documentación y las Reglas de Agente (.agent/rules) para obligar a cualquier instancia de Gemini a leer el contexto antes de trabajar.
>
> ## 1. Estructura de Archivos a Generar
> Analiza el repositorio (@workspace) y genera el contenido para estos archivos. Si no puedes crearlos directamente, dame el código Markdown de cada uno:
>
> /memory-bank/
> projectbrief.md (Visión general del proyecto)
> productContext.md (Contexto de negocio y usuarios)
> systemPatterns.md (Arquitectura y diseño técnico)
> techContext.md (Stack, herramientas y comandos)
> activeContext.md (El estado actual "en vivo" del desarrollo)
> progress.md (Historial de cambios y deuda técnica)
>
> /.agent/rules/
> 00-memory-bank.md (Regla maestra de lectura obligatoria)
>
> ## 2. Definición del Contenido (Archivos Core)
>
> ### memory-bank/projectbrief.md
> Resumen ejecutivo.
> Objetivos clave.
>
> ### memory-bank/activeContext.md
> Crítico: Este archivo actúa como semáforo.
> Debe contener: "¿En qué estamos trabajando AHORA MISMO?"
> Lista de tareas activas.
> Próximos pasos inmediatos.
>
> ### memory-bank/systemPatterns.md
> Arquitectura del sistema.
> Mapa de carpetas clave.
> Relaciones entre módulos (quién depende de quién).
>
> ## 3. Configuración de la Regla (.agent/rules)
>
> Genera el archivo .agent/rules/00-memory-bank.md con el siguiente contenido EXACTO. Esto es lo que forzará a los agentes a comportarse correctamente:
>
> ---
> description: "Mandatory Memory Bank Workflow"
> globs: ["**/*"]
> alwaysApply: true
> priority: critical
> ---
>
> # AGENT MANDATE: Shared Memory Access
>
> You are working in a multi-agent environment (Antigravity). You must rely on the Memory Bank for the single source of truth.
>
> ## 1. Context Loading (READ FIRST)
> Before planning or executing ANY task, you MUST read:
> - memory-bank/activeContext.md -> To understand current focus.
> - memory-bank/systemPatterns.md -> To respect architecture.
> - memory-bank/techContext.md -> To use correct tools/commands.
>
> ## 2. Atomic Updates (WRITE BACK)
> After completing a task:
> 1. Update memory-bank/activeContext.md: Remove your finished task, add the result.
> 2. Update memory-bank/progress.md: Mark features as completed.
> 3. Self-Correction: If you find projectbrief.md or systemPatterns.md outdated, update them immediately.
>
> ## 3. Forbidden Actions
> - Do not invent commands not listed in techContext.md.
> - Do not modify core architecture without updating systemPatterns.md first.
>
> ## 4. Procedimiento de Inicialización
> 1. Ejecuta un escaneo profundo del repositorio.
> 2. Redacta el contenido de todos los archivos de /memory-bank/ basándote en el código existente.
> 3. Crea la carpeta .agent/rules/ y el archivo de reglas.
> 4. Confírmame cuando el "Cerebro del Proyecto" esté activo.

**Resumen de la Respuesta/Acción:**
Se ha generado la estructura completa del Memory Bank en `/memory-bank/` y se ha creado la regla obligatoria en `.agent/rules/00-memory-bank.md` para asegurar la consistencia del contexto entre agentes.
---

## 002 - Recuperación de Log de Prompts
**Fecha:** 2026-02-02 06:24
**Prompt Original:**
> Se te ha olvidado el registro del prompt en un archivo `prompts-log.md`. recuerda que todos los prompts deben ser almacenados

**Resumen de la Respuesta/Acción:**
Se ha identificado que el archivo de logs oficial es `prompts/prompts.md` (aunque se solicitó `prompts-log.md`). Se han registrado retroactivamente los prompts de la sesión actual.
---
