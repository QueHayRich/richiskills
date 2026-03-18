# Tony — Asistente de Modelado Molecular In Silico — Roadmap

## Estado actual: Borrador v1 (2026-03-18)

Tony tiene la estructura base y el conocimiento general definido, pero falta agregar protocolos específicos, scripts y documentos de referencia.

---

## Qué hace hoy

- Se activa con `/tony` y responde como experto en modelado in silico
- Cubre: preparación de sistemas, docking, dinámica molecular, energía libre, visualización
- Genera scripts bash/python/tcl/pml listos para ejecutar
- Adapta comandos al SO del usuario (Ubuntu/macOS/Windows)
- Prioriza flujos de trabajo por CLI (sin GUI)
- Guarda lecciones aprendidas en `~/.claude/tony/lessons_learned.md`

## Software soportado

GROMACS, AutoDock/Vina, UCSF Chimera, VMD, PyMOL, OpenMM, MDAnalysis, AlphaFold, ACPYPE, SwissParam, Open Babel, Avogadro

---

## Pendientes prioritarios

### Protocolos de referencia (agregar a `references/`)
- [ ] Protocolo estándar de docking con AutoDock Vina (CLI completo)
- [ ] Protocolo de validación de docking: re-docking, cross-docking, curvas de enriquecimiento
- [ ] Protocolo de MD con GROMACS: desde PDB hasta análisis de producción
- [ ] Protocolo de parametrización de ligandos con ACPYPE/GAFF
- [ ] Protocolo de MMGBSA/MMPBSA con gmx_MMPBSA
- [ ] Protocolo de FEP y umbrella sampling
- [ ] Guía de force fields: cuándo usar AMBER, CHARMM, OPLS-AA y por qué

### Scripts reutilizables (agregar a `scripts/`)
- [ ] Script PyMOL (.pml): generar caja de docking y exportar coordenadas a JSON/txt
- [ ] Script bash: pipeline completo de docking Vina desde terminal
- [ ] Script bash: preparación de sistema GROMACS (pdb2gmx → solvate → ions → em)
- [ ] Script python: parsear output de Vina → ranking de afinidades → CSV/JSON
- [ ] Script python: generar complejo proteína-ligando PDB desde resultado de docking
- [ ] Script PyMOL (.pml): renderizado de calidad publicación del complejo final
- [ ] Script tcl (VMD): análisis de trayectorias MD (RMSD, RMSF, puentes H)
- [ ] Script python: pipeline de análisis con MDAnalysis

### Mejoras a la skill
- [ ] Agregar sección de troubleshooting: errores comunes en GROMACS, Vina, parametrización
- [ ] Agregar decisiones de diseño: ¿cuándo usar docking rígido vs. flexible? ¿cuándo MD es necesaria y cuándo no?
- [ ] Agregar sección de AlphaFold: cuándo usar, cómo evaluar la calidad del modelo (pLDDT, PAE), preparación post-predicción
- [ ] Mejorar sección de visualización PyMOL: paletas de colores para publicación, representaciones estándar por tipo de análisis

### Pruebas
- [ ] Probar pipeline completo de docking con un sistema conocido (ej. HIV-1 protease + inhibidor)
- [ ] Probar generación de scripts GROMACS con un caso real
- [ ] Probar análisis de trayectoria MD con datos existentes
- [ ] Verificar que los scripts generados corren sin errores en Ubuntu y macOS

---

## Ideas a futuro

### Pipeline de docking automatizado por CLI
La visión: un flujo completamente automatizado desde terminal:
```
1. PyMOL: abrir proteína → definir sitio → exportar caja a JSON
2. Terminal: preparar ligandos (obabel) → preparar receptor (prepare_receptor)
3. Terminal: ejecutar Vina con parámetros del JSON
4. Python: parsear resultados → ranking → top N poses
5. Python: generar complejos PDB (proteína + mejor pose)
6. PyMOL: renderizar imagen final con script .pml
```
Todo esto debería poder orquestarse con un solo script maestro.

### Integración con MCP + biblioteca de papers
- Base de datos vectorial con papers clave de cada área (docking, MD, FEP)
- Tony consulta la literatura para justificar recomendaciones de parámetros
- Permite preguntas como: "¿qué force field usaron los últimos 5 papers de FEP en GPCR?"

### Integración con scientific-article-reviewer
- Cuando el reviewer detecte un paper de modelado in silico, Tony puede aportar la revisión metodológica especializada

### Protocolos personalizados
- A medida que Richie desarrolle y valide sus propios protocolos, guardarlos en `references/` como la fuente de verdad
- Estos protocolos sustituyen las recomendaciones genéricas cuando existen

### Soporte para HPC
- Templates de scripts para SLURM/PBS
- Estimación de recursos (cores, RAM, tiempo) según tamaño del sistema
- Tips para optimizar GROMACS en clusters

---

## Notas de diseño

- Tony responde en español con términos técnicos en inglés (docking, force field, binding affinity, etc.)
- Prioriza software gratuito siempre; puede mencionar alternativas comerciales (Schrödinger, MOE) como referencia pero no las recomienda por defecto
- Los scripts deben ser autocontenidos: encabezado con propósito, dependencias, y cómo ejecutar
- Las lecciones aprendidas se guardan en `~/.claude/tony/lessons_learned.md`, NO en el repo (son personales)
- Las `references/` y `scripts/` se irán poblando iterativamente conforme se vayan creando y validando
