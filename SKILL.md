# 🔍 research-frameworks Skill

**Versión**: 1.0.0  
**Última actualización**: Abril 2026  
**Estado**: Producción

---

## ¿Qué es research-frameworks?

Una **Skill de investigación estructurada** que automatiza el proceso de benchmarking de frameworks, librerías y herramientas para cualquier dominio técnico.

### El Problema que Resuelve

Cuando necesitas elegir entre múltiples opciones (frameworks de backend, librerías de visualización, herramientas de IA, etc.), investigar manualmente consume **3-4 horas** entre:
- Búsquedas dispersas en GitHub
- Lectura de threads en Reddit
- Revisión de blogs técnicos
- Compilación de pros/contras

**Esta Skill lo hace en 20-30 minutos** mediante investigación sistemática y análisis comparativo.

---

## 📋 Casos de Uso

✅ Elegir frameworks backend (Django, Flask, FastAPI, etc.)  
✅ Comparar librerías frontend (React, Vue, Angular, Svelte)  
✅ Evaluar herramientas de IA/ML para casos específicos  
✅ Seleccionar soluciones DevOps/Infrastructure  
✅ Investigar librerías de data science  
✅ Benchmarking de APIs externas  
✅ Evaluar pilas tecnológicas para proyectos nuevos  

---

## 🎯 Cómo Usar Esta Skill

### Entrada (User Prompt)

```
Investiga frameworks para [caso de uso específico]

Ejemplo:
"Investiga frameworks para construir dashboards interactivos en Python,
considerando facilidad de uso, rendimiento y documentación para usuario no-técnico"
```

### Proceso Automático (Qué hace la Skill)

1. **Identificación de opciones** → Busca 4-6 alternativas principales
2. **Investigación en fuentes reales** → GitHub (starred repos, issues, commits), Reddit, blogs técnicos
3. **Evaluación estructurada** → Usa matriz comparativa con criterios ponderados
4. **Recomendación contextual** → Proporciona árboles de decisión por perfil

### Salida (Qué Recibes)

- Tabla comparativa detallada (pros/contras/comunidad/curva)
- Árbol de decisión personalizado por caso de uso
- 2-3 ejemplos de código reales
- Links verificados a recursos
- Roadmap de aprendizaje

---

## 🏗️ Arquitectura de la Investigación

### Fases de Ejecución

```
┌─────────────────────────────────────────────────────┐
│ 1. BRIEFING                                         │
│ - Extraer requisitos del caso de uso                │
│ - Identificar restricciones (escala, costo, etc)    │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 2. INVESTIGACIÓN MULTI-FUENTE                       │
│ - GitHub: popularity, maintenance, issues          │
│ - Reddit: real-world experiences, pain points      │
│ - Blogs: technical deep-dives, migrations          │
│ - Docs: clarity, examples, community               │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 3. COMPILACIÓN DE DATOS                             │
│ - Matriz comparativa normalizada                    │
│ - Scoring por criterio                              │
│ - Identificación de trade-offs                      │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 4. SÍNTESIS Y RECOMENDACIÓN                         │
│ - Árbol de decisión por perfil                      │
│ - Ejemplos de código funcionales                    │
│ - Roadmap de adopción                               │
└─────────────────────────────────────────────────────┘
```

---

## 📐 Matriz de Evaluación (Criterios por Defecto)

| Criterio | Peso | Escala | Descripción |
|----------|------|--------|-------------|
| **Curva de Aprendizaje** | 20% | 1-10 | Qué tan rápido aprende un dev típico |
| **Comunidad & Soporte** | 20% | 1-10 | Tamaño, respuesta en issues, docs |
| **Mantenimiento Activo** | 15% | 1-10 | Releases recientes, velocidad de fixes |
| **Performance** | 15% | 1-10 | Benchmarks reales vs competencia |
| **Escalabilidad** | 15% | 1-10 | Capacidad para crecer sin reescrituras |
| **Ecosistema** | 10% | 1-10 | Plugins, extensiones, integraciones |
| **Documentación** | 5% | 1-10 | Claridad, ejemplos, guías |

**Nota**: Los pesos se ajustan según el contexto de tu proyecto.

---

## 🔧 Uso Avanzado: Personalizar la Investigación

### Cambiar Criterios de Evaluación

Si tu caso requiere prioridades diferentes, especifica:

```
Investiga [frameworks] PERO:
- Prioriza escalabilidad (30%) sobre curva de aprendizaje (10%)
- Incluye costos de licencia como criterio (20%)
- Requiere compatibilidad con [tecnología X] (obligatorio)
```

### Filtros Específicos

```
Investiga frameworks de visualización Python PERO:
- Solo opciones open-source
- Con soporte activo en últimos 6 meses
- Documentado en español o inglés
- No incluyas alternativas propietarias
```

---

## 📊 Estructura de Salida Esperada

Después de usar esta Skill, recibirás un documento con esta estructura:

### 1. Executive Summary (1 página)
- Recomendación principal con justificación
- Alternativa secundaria
- Casos donde cada opción es superior

### 2. Tabla Comparativa (detallada)
- Filas: frameworks
- Columnas: criterios evaluados
- Scores normalizados + fuentes

### 3. Árbol de Decisión
```
¿Necesitas máximo rendimiento?
├─ Sí → [Framework A] (véase caso de uso X)
└─ No → ¿Prioriza facilidad de uso?
    ├─ Sí → [Framework B] (mejor docs)
    └─ No → [Framework C] (balance)
```

### 4. Ejemplos de Código
- 2-3 ejemplos progresivos (hello world → feature real)
- Cada ejemplo documentado
- Links a repos públicos

### 5. Roadmap de Adopción
- Semana 1-2: Fundamentos
- Semana 3-4: Proyecto pequeño
- Semana 5+: Escalar

### 6. Referencias Verificadas
- Links a documentación oficial
- Threads de Reddit relevantes
- Repos GitHub destacados
- Articles con insights

---

## 🎓 Ejemplos de Uso Completo

### Ejemplo 1: Backend API Framework
**Entrada:**
```
Investiga frameworks Python para construir API REST scalable
que vaya a producción en 3 meses con equipo de 2 devs
```

**Salida esperada:**
- Comparativa: Django REST, FastAPI, Flask + Connexion, Falcon
- Recomendación: FastAPI (mejor para timeline corto)
- Árbol de decisión: Según necesidad de ORM
- 3 ejemplos: API auth, CRUD básico, middleware

---

### Ejemplo 2: Frontend State Management
**Entrada:**
```
Investiga librerías de state management para React SPA
con 50+ páginas y caché offline-first
```

**Salida esperada:**
- Comparativa: Redux, Zustand, Jotai, Recoil, MobX
- Matriz: Bundle size, learning curve, DX, performance
- Recomendación por perfil (junior vs senior)
- Ejemplos con offline support

---

## 🚀 Triggers que Activan Esta Skill

La Skill se activa cuando detecta:

- Preguntas de selección: "¿Cuál es mejor entre...?"
- Investigaciones: "Investiga frameworks para..."
- Evaluaciones: "Compara X vs Y vs Z"
- Decisiones técnicas: "Ayúdame a elegir tech stack"
- Due diligence: "Evalúa opciones de [categoria]"

Uso explícito: Simplemente escribe `/research-frameworks` seguido de tu pregunta.

---

## 📚 Archivos en Esta Skill

```
research-frameworks/
├── SKILL.md                          ← Estás aquí
├── TRIGGERS.md                       ← Patrones de activación
├── FRAMEWORKS.json                   ← Matriz comparativa (estructura)
├── assets/
│   ├── comparison_matrix.md          ← Template de matriz
│   ├── decision_tree.md              ← Generador de árboles
│   └── templates/
│       ├── evaluation_rubric.json
│       └── output_template.md
├── scripts/
│   ├── analyze_github.py             ← Análisis de repos
│   ├── evaluate_complexity.py        ← Scoring automático
│   └── benchmark_runner.sh           ← Ejecutor de tests
├── examples/
│   ├── case_study_1.md               ← Backend frameworks
│   ├── case_study_2.md               ← Frontend libraries
│   └── quick_start.md                ← Primeros pasos
└── CHANGELOG.md                      ← Historia de versiones
```

---

## 🔄 Workflow Típico (5 pasos)

### Paso 1: Briefing (5 min)
Tú especificas: qué necesitas, restricciones, timeline

### Paso 2: Investigación (15 min)
Yo busco en: GitHub, Reddit, blogs técnicos, docs oficiales

### Paso 3: Compilación (10 min)
Yo creo: matriz comparativa, scoring, análisis

### Paso 4: Síntesis (8 min)
Yo genero: árboles de decisión, ejemplos, roadmap

### Paso 5: Entrega (2 min)
Yo presento: recomendación + justificación + alternativas

**Total: ~40 minutos**

---

## ⚙️ Configuración Avanzada

### Ajustar Fuentes de Investigación

Por defecto uso: GitHub ⭐ Reddit 📱 Blogs técnicos 📝

Puedes especificar: "Solo GitHub + documentación oficial" o "Incluye Twitter/X"

### Ajustar Criterios de Evaluación

Matriz por defecto: 7 criterios estándar

Personalizable: Añadir/quitar criterios según tu contexto

### Ajustar Profundidad

- **Light** (20 min): 3-4 opciones, análisis superficial
- **Standard** (40 min): 5-6 opciones, análisis completo ← DEFECTO
- **Deep** (90 min): 8+ opciones, análisis exhaustivo, benchmarks

---

## 📝 Notas sobre Calidad

✅ **Basado en evidencia**: Cada claim tiene fuente verificable  
✅ **Sin sesgos**: Destaco trade-offs reales, no favorecerismo  
✅ **Actualizado**: Información de últimos 6 meses mínimo  
✅ **Contextual**: Recomendaciones adaptadas a TU caso  
✅ **Reproducible**: Puedes verificar todas las fuentes  

---

## 🤝 Contribuciones

¿Encontraste un error? ¿Una opción mejor? ¿Un criterio faltante?  
Este documento se mejora continuamente. Tus sugerencias son bienvenidas.

---

## 📞 Soporte y Preguntas

Si tienes dudas sobre:
- **Cómo usar la Skill**: Ver `examples/quick_start.md`
- **Qué casos cubre**: Ver casos de uso arriba ↑
- **Cómo personalizar**: Ver "Uso Avanzado" ↑
- **Resultados inesperados**: Revisar `TRIGGERS.md` para clarificar

---

**Última actualización**: Abril 2026  
**Mantenida por**: Wei (Weiming Chu)  
**Licencia**: MIT (libre para usar y modificar)
