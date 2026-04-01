# 🎯 TRIGGERS.md - Patrones de Activación

Este documento define cuándo y cómo se activa automáticamente la Skill `research-frameworks`.

---

## Activación Automática

La Skill se activa cuando detecta estos patrones:

### 1. Preguntas de Selección Comparativa

**Patrón**: "¿Cuál es mejor/mejor entre X, Y, Z?"

✅ Ejemplos que activan:
```
- "¿Cuál es mejor: React o Vue?"
- "Entre Django y FastAPI, ¿cuál elijo?"
- "PostgreSQL vs MongoDB para mi caso?"
- "¿Debo usar Kubernetes o Docker Swarm?"
```

❌ NO activa si:
- Es una pregunta teórica sin contexto ("¿Python o JavaScript?")
- Necesita respuesta simple ("¿Cuál es más rápido, A o B?")

---

### 2. Investigación Abierta

**Patrón**: "Investiga/Explora [categoría] para [caso de uso]"

✅ Ejemplos que activan:
```
- "Investiga frameworks Python para dashboard analytics"
- "Explora alternativas a Make.com para automatización"
- "Busca librerías de gráficos para time-series data"
- "Investiga soluciones de vending machine management"
```

**Nivel de detalle**:
- Caso de uso específico → investigación profunda
- Caso genérico → investigación estándar
- Con restricciones → investigación filtrada

---

### 3. Decisiones Técnicas

**Patrón**: "Necesito elegir tech stack para..."

✅ Ejemplos que activan:
```
- "Necesito elegir framework backend para SaaS"
- "Ayúdame a escoger herramientas para mi CLI"
- "¿Qué stack es mejor para startup de ecommerce?"
- "Debo decidir entre soluciones propietarias y open-source"
```

---

### 4. Evaluación y Benchmarking

**Patrón**: "Evalúa / Compara / Benchmarquea [opciones]"

✅ Ejemplos que activan:
```
- "Evalúa estos 5 frameworks según rendimiento"
- "Crea una tabla comparativa de librerías"
- "Benchmarquea opciones de CI/CD"
- "Compara costos entre servicios X, Y, Z"
```

---

### 5. Due Diligence / Análisis de Riesgos

**Patrón**: "¿Es buena decisión usar X para...?"

✅ Ejemplos que activan:
```
- "¿Es buena idea adoptar Rust para nuestro backend?"
- "¿Qué riesgos tiene elegir esta librería poco conocida?"
- "¿Deberíamos migrar a este nuevo framework?"
- "¿Es escalable esta solución para crecer 10x?"
```

---

## Activación Explícita

Usa el comando `/research-frameworks` para forzar activación:

```
/research-frameworks: Investiga herramientas de IA para procesamiento de PDFs
```

**Útil cuando**:
- La pregunta es ambigua
- Necesitas garantizar que se active la Skill
- Quieres investigación extra profunda

---

## Desactivación (Casos a evitar)

La Skill **NO se activa** para:

❌ Preguntas teóricas sin contexto
```
"¿Qué es un framework?"
"¿Cuándo usar Python vs JavaScript?"
```

❌ Problemas técnicos específicos
```
"¿Por qué me da este error en React?"
"¿Cómo debuggeo este módulo de Express?"
```

❌ Tutoriales o enseñanza básica
```
"Enséñame a usar Django"
"Quiero aprender React desde cero"
```

❌ Comparativas muy simples
```
"¿A o B? (sin contexto)"
"¿Cuál es más rápido?"
```

---

## Parámetros de Personalización

Añade estos modificadores para ajustar la investigación:

### Profundidad
```
- "Investiga (LIGHT): ..." → 20 min, 3-4 opciones
- "Investiga (STANDARD): ..." → 40 min, 5-6 opciones (defecto)
- "Investiga (DEEP): ..." → 90 min, 8+ opciones
```

### Restricciones
```
- "... PERO SOLO open-source"
- "... PERO mantienen presupuesto bajo $X"
- "... PERO compatible con [tecnología]"
```

### Fuentes
```
- "... basa en: GitHub, Reddit, blogs"
- "... solo documentación oficial"
- "... incluye tweets/artículos recientes"
```

### Formato
```
- "... dame tabla comparativa"
- "... dame árbol de decisión"
- "... dame pros/contras por opción"
```

---

## Ejemplos de Disparo Correcto

### Ejemplo 1: Completo
```
/research-frameworks

Investiga (STANDARD) herramientas de análisis de logs para ecommerce
CON restricciones:
- Presupuesto: <$100/mes
- Team: 2 devs junior
- Scale: 100K req/día
PERO:
- Dashboards intuitivos
- Soporte activo en Discord/GitHub
FORMATO: Tabla + árbol de decisión + 2 ejemplos
```

### Ejemplo 2: Simple
```
Investiga frameworks Python para dashboards,
necesito algo que aprenda en 1 semana
```

### Ejemplo 3: Específico
```
Estoy eligiendo entre Bamboo de Maracaibo o
sistema propio para vending machine management.
Investiga soluciones SaaS vs custom.
```

---

## Detección de Contexto

La Skill analiza **contexto previo** en la conversación:

✅ Si anteriormente hablaste de:
- Proyecto específico → personaliza recomendaciones
- Tech stack existente → sugiere opciones compatibles
- Timeline/presupuesto → filtra opciones

---

## Activación en Casos Borderline

Para preguntas "en el límite", la Skill se activa si hay:

✔ **Contexto claro** (proyecto real, restricciones)
✔ **Propósito de decisión** (necesito elegir, estoy dudando)
✔ **Múltiples opciones** (3+ alternativas implícitas)

---

## Notas Importantes

1. **Una Skill, muchos dominios**: Funciona para backend, frontend, DevOps, IA, etc.

2. **Complementaria, no reemplazante**: Si necesitas debug específico, usa otras Habilidades.

3. **Mejora continua**: Los triggers se ajustan con uso real. Feedback bienvenido.

4. **Idioma flexible**: Funciona en español e inglés.

---

**Última actualización**: Abril 2026
