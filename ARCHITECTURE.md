# 🏗️ ARCHITECTURE.md

Documentación técnica interna de cómo funciona la Skill `research-frameworks`.

---

## Sistema General

```
┌────────────────────────────────────────────────────────┐
│                  research-frameworks                   │
│                   (Claude Skill)                       │
└────────────────────────────────────────────────────────┘
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
        ▼                 ▼                 ▼
    [INPUT]          [PROCESS]         [OUTPUT]
    
    - User prompt     - Briefing        - Matriz
    - Context         - Research        - Árbol decisión
    - Constraints     - Compilation     - Ejemplos
                      - Synthesis       - Roadmap
```

---

## Fases de Ejecución Detalladas

### Fase 1: BRIEFING (5 minutos)

**Input**: Pregunta del usuario

**Proceso**:
1. Parse de pregunta → extraer intención
2. Identificar dominio (backend, frontend, DevOps, etc)
3. Extraer restricciones:
   - Team size
   - Timeline
   - Budget
   - Compatibility requirements
   - Performance needs
4. Identificar 4-6 opciones principales para evaluar

**Output**: 
```json
{
  "domain": "backend-apis",
  "case": "RESTful API Framework Selection",
  "constraints": {
    "teamSize": 2,
    "timeline": "3 months",
    "budget": "open-source"
  },
  "candidates": ["FastAPI", "Django REST", "Flask + Connexion"]
}
```

---

### Fase 2: INVESTIGACIÓN (15 minutos)

**Input**: Lista de candidatos + restricciones

**Proceso por cada candidato**:

#### 2a. GitHub Mining
- Stars ⭐ (popularidad)
- Issues recientes (actividad)
- Commits últimos 3 meses (mantenimiento)
- Contributors (salud del proyecto)
- PRs pendientes (velocidad)
- Releases recientes (versioning)

**Fuente**: GitHub API + web scraping repos top-tier

#### 2b. Reddit Analysis
- Threads comparativos (experiencias reales)
- Pain points mencionados (problemas comunes)
- Use cases (aplicaciones reales)
- Team size recommendations (escalabilidad)

**Fuente**: r/learnprogramming, r/webdev, comunidades específicas

#### 2c. Blog/Medium Research
- Technical deep-dives
- Migration stories
- Benchmarks
- Lessons learned

**Fuente**: Dev.to, Medium, HashNode, technical blogs

#### 2d. Official Documentation
- Clarity score (1-10)
- Completeness (API coverage)
- Examples quality
- Community resources

**Fuente**: Documentación oficial + wikis

**Output por candidato**:
```json
{
  "name": "FastAPI",
  "github_stars": 71000,
  "last_commit": "2024-11",
  "activity_level": "very-active",
  "reddit_sentiment": "positive",
  "blog_mentions": 45,
  "doc_quality": 9
}
```

---

### Fase 3: COMPILACIÓN (10 minutos)

**Input**: Datos de investigación de 5-6 candidatos

**Proceso**:

#### 3a. Scoring Individual
Para cada candidato, cada criterio:
```
Score = (métrica normalizada 0-10) × peso del criterio

Ejemplo:
- Curva de aprendizaje: 9/10 × 0.20 = 1.8
- Community: 8/10 × 0.20 = 1.6
- Performance: 9/10 × 0.15 = 1.35
... total = 8.45/10
```

**Escala normalizada**: 
- 9-10: Excelente
- 7-8: Muy bueno
- 5-6: Aceptable
- 3-4: Debajo del promedio
- 1-2: Evitar

#### 3b. Matriz Comparativa
```
Framework    | Learning | Community | Active | Perf | Scale | Eco | Docs | Score
─────────────┼──────────┼───────────┼────────┼──────┼───────┼─────┼──────┼──────
FastAPI      |    9     |     8     |   9    |  9   |   8   |  7  |  9   | 8.45
Django REST  |    6     |    10     |   9    |  7   |   8   | 10  |  9   | 8.30
Flask+Connex |    8     |     8     |   8    |  7   |   7   |  8  |  7   | 7.60
```

#### 3c. Trade-offs Analysis
Identifica dónde cada opción gana/pierde:

```
FastAPI wins at:
- Performance (async/await)
- Learning curve
- Modern APIs

Django REST wins at:
- Ecosystem size
- Admin panel
- Mature tooling
```

**Output**: FRAMEWORKS.json (matriz completa)

---

### Fase 4: SÍNTESIS (8 minutos)

**Input**: Matriz + contexto del usuario

**Proceso**:

#### 4a. Árbol de Decisión
```
IF timeline < 3 months:
  → FastAPI (learn fast)
ELSE IF team > 10 devs:
  → Django REST (large ecosystem)
ELSE IF performance critical:
  → FastAPI (benchmarks 3x mejor)
ELSE:
  → Default recommendation
```

#### 4b. Ejemplos de Código
Para cada framework top-3:
- Hello World (simple intro)
- CRUD API (intermediate)
- Production features (advanced)

Fuente: Repositorios públicos verificados

#### 4c. Roadmap de Adopción
```
Week 1-2: Learn basics (setup, routing, models)
Week 3-4: Build small project (CRUD app)
Week 5-6: Production features (auth, error handling, tests)
Week 7-8: Deploy to production
```

#### 4d. Recomendación Final
```
PRIMARY: FastAPI
REASON: Meets timeline (learn in 1-2 weeks), 
        performance matters (async), 
        small team ideal

SECONDARY: Django REST
REASON: If you need admin panel or ecosystem

FALLBACK: Flask + Connexion
REASON: Maximum flexibility needed
```

**Output**: Documento estructurado con todo lo anterior

---

## Matriz de Evaluación: Criterios Detallados

### 1. Curva de Aprendizaje (20%)

**Medición**:
- Complejidad de conceptos base
- Documentación introductoria
- Número de abstracción layers
- Reddit: "how long to learn?"

**Scoring**:
- 10: Puede aprender en < 1 semana
- 8: 2-3 semanas
- 6: 3-4 semanas
- 4: > 1 mes

### 2. Comunidad & Soporte (20%)

**Medición**:
- Tamaño de comunidad (GitHub stars)
- Respuesta en issues (avg días)
- Discord/Slack members
- Reddit activity
- Stack Overflow questions

**Scoring**:
- 10: 10k+ issues cerrados/año, <12h respuesta
- 8: 5k+, <24h
- 6: 2k+, <48h
- 4: <1k, >48h

### 3. Mantenimiento Activo (15%)

**Medición**:
- Commits últimos 3 meses
- Pull requests aprobados
- Issues cerrados
- Release frequency

**Scoring**:
- 10: Commits cada semana, releases cada mes
- 8: Commits cada 2 semanas, releases cada 2 meses
- 6: Commits cada mes
- 4: <1 commit/mes (inactivo)

### 4. Performance (15%)

**Medición**:
- Benchmarks reales (req/sec)
- Memory usage
- CPU usage
- Comparison vs competitors

**Scoring**:
- 10: Top performer vs benchmarks
- 8: Above average
- 6: Average
- 4: Below average

### 5. Escalabilidad (15%)

**Medición**:
- Usado por empresas grandes
- Caso de uso large-scale
- Horizontal scaling support
- Database scalability

**Scoring**:
- 10: Escala a millones de req/día
- 8: Escala a cientos de mil
- 6: Escala a decenas de mil
- 4: Escala limitada

### 6. Ecosistema (10%)

**Medición**:
- Número de librerías/plugins
- Integraciones
- Middleware disponibles
- Community-built tools

**Scoring**:
- 10: Thousands of packages (npm, PyPI)
- 8: Hundreds
- 6: Dozens
- 4: Few

### 7. Documentación (5%)

**Medición**:
- Official docs completeness (0-100%)
- Examples quality
- Tutorial availability
- API clarity

**Scoring**:
- 10: Complete, clear, many examples
- 8: Good, some gaps
- 6: Acceptable
- 4: Incomplete

---

## Fuentes y Confiabilidad

### Confiabilidad por Fuente

| Fuente | Confiabilidad | Peso | Usada para |
|--------|--------------|------|-----------|
| GitHub | 95% | 30% | Stars, activity, community |
| Reddit | 80% | 25% | Real experiences, pain points |
| Oficial Docs | 98% | 25% | Features, reliability |
| Blogs | 70% | 20% | Comparativas, lessons learned |

### Validación de Datos

Cada claim debe tener:
- ✅ Fuente verificable
- ✅ Fecha reciente (<6 meses)
- ✅ Links públicos
- ✅ Sin sesgo aparente

Descartamos:
- ❌ Claims sin fuente
- ❌ Datos > 1 año de antigüedad
- ❌ Opiniones personales no documentadas
- ❌ Benchmarks caseros no reproducibles

---

## JSON Structure (FRAMEWORKS.json)

```json
{
  "metadata": {
    "skillName": "research-frameworks",
    "domain": "backend-apis",
    "case": "RESTful API Framework Selection"
  },
  
  "briefing": {
    "caseOfUse": "...",
    "constraints": {...},
    "priorities": {...}
  },
  
  "frameworks": [
    {
      "id": "fastapi",
      "name": "FastAPI",
      "scores": {
        "learningCurve": 9,
        "communitySupport": 8,
        ... (7 criteria)
      },
      "weighted_score": 8.45,
      "pros": [...],
      "cons": [...],
      "community": {...},
      "references": [...]
    },
    ... (more frameworks)
  ],
  
  "decisionTree": {
    "root": {...},
    "branches": {...}
  },
  
  "verdict": {
    "primary": "FastAPI",
    "primary_reason": "...",
    "secondary": "...",
    "fallback": "..."
  }
}
```

---

## Flujo de Control

```
User Question
    │
    ├─→ [BRIEFING]
    │   ├─→ Parse input
    │   ├─→ Extract constraints
    │   └─→ Identify candidates
    │
    ├─→ [INVESTIGATION]
    │   ├─→ GitHub mining
    │   ├─→ Reddit analysis
    │   ├─→ Blog research
    │   └─→ Doc evaluation
    │
    ├─→ [COMPILATION]
    │   ├─→ Score normalization
    │   ├─→ Weighting application
    │   ├─→ Matrix generation
    │   └─→ Trade-offs analysis
    │
    ├─→ [SYNTHESIS]
    │   ├─→ Decision tree creation
    │   ├─→ Code examples
    │   ├─→ Adoption roadmap
    │   └─→ Final recommendation
    │
    └─→ [DELIVERY]
        └─→ Structured document
```

---

## Extensibilidad

### Agregar Nuevo Criterio

1. Definir métrica en `evaluation_rubric.json`
2. Agregar scoring logic
3. Ajustar pesos totales (suma = 100%)
4. Documentar en SKILL.md

Ejemplo:
```json
{
  "criterion": "Cost",
  "weight": 0.15,
  "scale": "1-10 or $USD",
  "measurement": "Pricing comparison"
}
```

### Agregar Nuevo Dominio

1. Crear branch nuevo en `FRAMEWORKS.json`
2. Defini candidates del dominio
3. Ejecutar investigación
4. Generar matriz
5. Documentar en `examples/case_study_X.md`

### Agregar Nueva Fuente

1. Integrar en [INVESTIGATION] phase
2. Definir extracción de datos
3. Normalizar scores
4. Documentar confiabilidad

---

## Performance & Optimizaciones

### Tiempo de Ejecución

| Fase | Tiempo | Optimización |
|------|--------|--------------|
| Briefing | 5 min | Parsing mejorado |
| Investigation | 15 min | Parallel searches |
| Compilation | 10 min | Pre-cached data |
| Synthesis | 8 min | Template library |
| Delivery | 2 min | Rendering |

**Total**: 40 minutos (STANDARD)

### Estrategias de Optimización

1. **Caching**: Top 50 frameworks pre-scored
2. **Parallel**: Búsquedas multi-fuente simultáneas
3. **Templates**: Plantillas pre-definidas
4. **Incremental**: Reusar análisis previos

---

## Limitaciones Conocidas

### Técnicas
- Investigación basada en datos públicos
- No accede a código privado de empresas
- Benchmarks pueden variar según contexto

### Alcance
- Requiere 3+ opciones para ser efectiva
- Mejor para framework/lib selection
- No reemplaza consultoría de arquitectura compleja

### Temporales
- Datos hasta enero 2025
- Comunidades pequeñas pueden no aparecer
- Benchmarks requieren contexto de hardware

---

## Testing & Validation

### Test Cases

```
✅ Backend frameworks selection
✅ Frontend libraries comparison
✅ DevOps tools evaluation
✅ Data science library selection
✅ IA/ML frameworks
✅ Niche domain tools
```

### Validation Checklist

- [ ] Scores normalizados (0-10)
- [ ] Pesos suman 100%
- [ ] Sources citadas
- [ ] Sin información contradictoria
- [ ] Ejemplos funcionales
- [ ] Links verificados
- [ ] Recomendación justificada

---

## Mejoras Futuras

### v1.1.0
- Stack Overflow API integration
- Automated benchmarking
- ML similarity scoring

### v2.0.0
- Real-time market analysis
- Trend forecasting
- Custom plugin system

---

**Última actualización**: Abril 2026  
**Versión**: 1.0.0 architecture
