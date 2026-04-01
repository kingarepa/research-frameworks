# 🔍 research-frameworks Skill

**Una herramienta profesional para investigación sistemática de frameworks, librerías y herramientas.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue)](./CHANGELOG.md)
[![Status](https://img.shields.io/badge/status-Production-brightgreen)](./CHANGELOG.md)

---

## 🎯 ¿Qué es research-frameworks?

Una **Skill de investigación estructurada** que automatiza el benchmarking de frameworks y herramientas tecnológicas mediante:

- 🔍 **Investigación multi-fuente**: GitHub, Reddit, blogs técnicos
- 📊 **Matrices comparativas normalizadas**: pros/contras/criterios
- 🌳 **Árboles de decisión**: recomendaciones contextuales
- 💾 **Ejemplos de código funcionales**: casos reales
- 📈 **Scoring objetivado**: basado en evidencia

**Ahorra 3-4 horas** de investigación manual en decisiones técnicas.

---

## ⚡ Quick Start (2 minutos)

### Ejemplo Básico
```
Investiga frameworks Python para dashboard analytics
```

### Ejemplo Específico
```
Necesito elegir entre FastAPI vs Django REST para API
Team: 2 devs, Timeline: 3 meses, Budget: open-source
```

### Ejemplo Complejo
```
Investiga (DEEP) herramientas de CI/CD
PERO presupuesto < $200/mes
PERO integración con GitHub/GitLab
PERO soporte para 500+ builds/día
```

👉 **[Lee Quick Start completo →](./examples/quick_start.md)**

---

## 📚 Documentación

| Documento | Propósito | Leer si... |
|-----------|-----------|-----------|
| **[SKILL.md](./SKILL.md)** | Guía completa | Quieres entender todo |
| **[TRIGGERS.md](./TRIGGERS.md)** | Patrones de activación | Necesitas claridad sobre cuándo activar |
| **[examples/quick_start.md](./examples/quick_start.md)** | Primeros pasos | Es tu primera vez |
| **[FRAMEWORKS.json](./FRAMEWORKS.json)** | Estructura de datos | Quieres entender formato |
| **[CHANGELOG.md](./CHANGELOG.md)** | Historial | Necesitas versioning |

---

## 🚀 Características

### ✨ Core Features
- ✅ Investigación sistemática en múltiples fuentes
- ✅ Matriz de evaluación con 7 criterios estándar
- ✅ Árbol de decisión contextual personalizado
- ✅ Scoring normalizado y ponderado
- ✅ Ejemplos de código reales + roadmap

### 🎛️ Personalización
- 🔧 Ajustar criterios de evaluación
- 🎚️ 3 niveles de profundidad (LIGHT, STANDARD, DEEP)
- 🏷️ Filtros por restricción
- 📐 Cambiar pesos de prioridad

### 🌐 Cobertura
- Backend frameworks (Django, FastAPI, Node.js, etc)
- Frontend libraries (React, Vue, Angular, Svelte)
- DevOps tools (Kubernetes, Docker, CI/CD)
- Data science (Pandas, TensorFlow, PyTorch)
- IA/ML frameworks
- Y muchas más categorías

---

## 📋 Estructura de Carpetas

```
research-frameworks/
├── SKILL.md                      ← Documentación principal
├── TRIGGERS.md                   ← Patrones de activación
├── FRAMEWORKS.json               ← Matriz comparativa (ejemplo)
├── CHANGELOG.md                  ← Historial de versiones
├── README.md                     ← Este archivo
│
├── assets/
│   ├── comparison_matrix.md      ← Template de matriz
│   ├── decision_tree.md          ← Generador de árboles
│   └── templates/
│       ├── evaluation_rubric.json
│       └── output_template.md
│
├── scripts/
│   ├── analyze_github.py         ← Análisis de repos (utils)
│   ├── evaluate_complexity.py    ← Scoring automático (utils)
│   └── benchmark_runner.sh       ← Ejecutor de tests (utils)
│
└── examples/
    ├── quick_start.md            ← Primeros pasos
    ├── case_study_1.md           ← Backend frameworks
    └── case_study_2.md           ← Frontend libraries (próximamente)
```

---

## 💡 Casos de Uso Típicos

### 1. Elegir Framework para Proyecto Nuevo
```
Investiga frameworks Python para construir API REST
que vaya a producción en 3 meses con equipo pequeño
```
→ Recibirás: comparativa, árbol de decisión, ejemplos, roadmap

### 2. Migración Tecnológica
```
Necesito evaluar si migrar de Django a FastAPI
Requisitos: mantener compatibilidad, ganar performance
```
→ Recibirás: análisis de riesgos, roadmap, consideraciones

### 3. Selección para Startup
```
Investiga (DEEP) soluciones de automatización
PERO open-source
PERO < $100/mes
PERO integración WhatsApp + Google Sheets
```
→ Recibirás: opciones filtradas, matriz, recomendación

### 4. Due Diligence Técnica
```
Evaluá alternativas a Kubernetes para orquestación
Compara riesgos, costos, curva de aprendizaje
```
→ Recibirás: análisis completo, benchmarks, verdict

---

## 🎓 Cómo Funciona

### Flujo Típico (40 minutos)

```
Tu pregunta
    ↓
[BRIEFING] - Extraer requisitos (5 min)
    ↓
[INVESTIGACIÓN] - Multi-fuente (15 min)
    ↓
[COMPILACIÓN] - Matriz + scoring (10 min)
    ↓
[SÍNTESIS] - Árbol + ejemplos (8 min)
    ↓
[ENTREGA] - Recomendación + justificación (2 min)
    ↓
Documento completo con análisis
```

---

## 🔍 Criterios de Evaluación (Por Defecto)

| Criterio | Peso | Escala |
|----------|------|--------|
| Curva de Aprendizaje | 20% | 1-10 |
| Comunidad & Soporte | 20% | 1-10 |
| Mantenimiento Activo | 15% | 1-10 |
| Performance | 15% | 1-10 |
| Escalabilidad | 15% | 1-10 |
| Ecosistema | 10% | 1-10 |
| Documentación | 5% | 1-10 |

**Customizable**: Puedes cambiar pesos según tu contexto

---

## ✅ Validación de Calidad

Esta Skill fue construida usando:

✅ **Investigación basada en evidencia** - Fuentes verificables  
✅ **Mejores prácticas documentadas** - De GitHub repos top-tier  
✅ **Arquitectura modular** - Fácil de extender  
✅ **Documentación clara** - 2000+ líneas, ejemplos incluidos  
✅ **Contexto específico** - Pensado para Wei + casos reales  

### Benchmarks de Calidad

| Métrica | Valor |
|---------|-------|
| Líneas de documentación | 2000+ |
| Ejemplos incluidos | 6+ |
| Criterios evaluados | 7 |
| Frameworks por análisis | 5-6 |
| Fuentes consultadas | 3+ |
| Tiempo de análisis | 40 min |

---

## 🛠️ Uso Avanzado

### Cambiar Profundidad
```
Investiga (LIGHT): ...     → 20 min, 3-4 opciones
Investiga (STANDARD): ...  → 40 min, 5-6 opciones (default)
Investiga (DEEP): ...      → 90 min, 8+ opciones
```

### Personalizar Criterios
```
PRIORITIZA: performance (40%), cost (30%), learning (30%)
IGNORE: ecosystem size
```

### Filtros
```
PERO solo open-source
PERO con comunidad activa (last commit < 30 días)
PERO documentación en español/inglés
```

---

## 📞 Preguntas Frecuentes

### ¿Cuándo usar esta Skill?
✅ Elegir entre 3+ opciones  
✅ Decisión técnica con restricciones  
✅ Necesitas justificación basada en datos  
✅ Timeline o presupuesto limitados

### ¿Cuándo NO usar?
❌ Preguntas teóricas sin contexto  
❌ Debugging de errores específicos  
❌ Aprender desde cero  
❌ Comparación simple (A vs B)

### ¿Cuánto tarda?
⏱️ LIGHT: 20 minutos  
⏱️ STANDARD: 40 minutos  
⏱️ DEEP: 90 minutos

### ¿Es precisa?
✅ Basada en fuentes verificables  
✅ Datos actuales (últimos 6 meses)  
✅ Sin sesgos (muestro trade-offs)  
✅ Reproducible (puedes verificar)

---

## 🚀 Próximas Mejoras (Roadmap)

### v1.1.0 (Q3 2026)
- Stack Overflow integration para Q&A
- Benchmarks automáticos
- ML para sugerencias de similares
- Más idiomas

### v1.2.0 (Q4 2026)
- API pública
- Dashboard interactivo
- Timeline tracking de tendencias
- Plugin system

### v2.0.0 (Q1 2027)
- Rediseño completo
- ML integration
- Real-time market analysis

---

## 📄 Licencia

MIT License - Libre para usar, modificar, distribuir

```
Copyright (c) 2026 Wei (Weiming Chu)

Permission is hereby granted, free of charge, to any person obtaining a copy...
```

---

## 🤝 Contribuciones

¿Encontraste un error? ¿Mejora sugerida? ¿Framework faltante?

Formas de contribuir:
1. **Reportar issues** → Describe qué falta/falló
2. **Sugerir frameworks** → Link a GitHub + descripción
3. **Mejorar documentación** → PRs bienvenidos
4. **Compartir casos** → Usa la Skill y feedback

---

## 📞 Contacto & Soporte

- **Documentación**: [SKILL.md](./SKILL.md)
- **Quick Start**: [quick_start.md](./examples/quick_start.md)
- **Triggers**: [TRIGGERS.md](./TRIGGERS.md)
- **Issues**: Reporta en CHANGELOG.md

---

## 🎯 Resumen

**research-frameworks** es tu asistente para tomar **decisiones tecnológicas informadas** basadas en **investigación sistemática** en **múltiples fuentes**.

Usa para elegir frameworks, evaluar alternativas, o validar decisiones.

**¡Comienza ahora!** → [Leer Quick Start](./examples/quick_start.md)

---

**Estado**: ✅ Producción  
**Versión**: 1.0.0  
**Última actualización**: Abril 2026  
**Mantenedor**: KingArepa
