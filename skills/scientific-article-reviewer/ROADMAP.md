# Scientific Article Reviewer — Roadmap

## Estado actual: Borrador v1 (2026-03-18)

La skill está funcional pero no probada con artículos reales.

---

## Qué hace hoy

- Lee artículos en PDF, Word o LaTeX
- Clasifica automáticamente el tipo de estudio y dominio científico
- Selecciona guía metodológica (PRISMA, CONSORT, STROBE, ARRIVE, estándares computacionales)
- Revisa: título, abstract, introducción, metodología, resultados, figuras, discusión
- Verifica citas buscándolas en internet (WebSearch) y las clasifica como ✅ ⚠️ ❌
- Genera reporte interno estructurado con recomendación (Accept / Minor / Major / Critical)
- Genera reporte para el editor (opcional, solo cuando lo pides) en formato genérico
- Guarda lecciones aprendidas en `~/.claude/scientific-reviewer/lessons_learned.md`

## Archivos de referencia incluidos

- `references/reporting-guidelines.md` — Checklists de PRISMA, CONSORT, STROBE, ARRIVE, estándares computacionales
- `references/editor-format-template.md` — Plantilla genérica del reporte para el editor

---

## Pendientes prioritarios

### Pruebas
- [ ] Probar con un artículo de química computacional que ya hayas revisado (para comparar resultados)
- [ ] Probar con una revisión sistemática para validar la detección de PRISMA
- [ ] Probar verificación de citas con un paper que tenga citas sospechosas o inventadas
- [ ] Evaluar tiempos: cuánto tarda la verificación de citas en un paper con 30-50 referencias

### Mejoras de contenido
- [ ] Agregar checklist específico para papers de docking molecular
- [ ] Agregar checklist específico para papers de dinámica molecular
- [ ] Agregar checklist para estudios de energía libre (FEP, MMGBSA, TI)
- [ ] Mejorar los criterios de interpretación de figuras (escalas, colores, resolución DPI)
- [ ] Agregar criterios para evaluar datos suplementarios

### Formato del editor
- [ ] Agregar templates específicos por editorial: Elsevier, Springer, ACS, RSC, Wiley
- [ ] Opción de exportar el reporte a Word (.docx) directamente
- [ ] Soportar formularios de revisión tipo checkbox (algunos journals los usan)

### Verificación de citas
- [ ] Optimizar la búsqueda: usar CrossRef API directamente para DOIs
- [ ] Agregar verificación de retractaciones (Retraction Watch)
- [ ] Detectar papers preprint vs. publicados
- [ ] Verificar si las citas son accesibles (open access vs. paywall)

### Autoevaluación y mejora continua
- [ ] Definir métricas de calidad de la revisión
- [ ] Crear un template de feedback post-revisión más estructurado
- [ ] Implementar comparación: tu revisión manual vs. la revisión de la skill (para calibrar)

---

## Ideas a futuro

- **MCP + RAG**: Conectar una base de datos vectorial con papers de referencia en cada área para que la skill pueda consultar literatura relevante durante la revisión
- **Multi-reviewer**: Simular un panel de revisores con diferentes perspectivas (metodológico, estadístico, de dominio)
- **Detección de plagio**: Integrar comparación de texto con bases de datos existentes
- **Integración con tony**: Cuando el artículo sea de modelado in silico, invocar automáticamente la expertise de tony para la revisión metodológica

---

## Notas de diseño

- La escala de recomendación tiene 4 niveles: Accept, Minor Revision, Major Revision, Critical (Critical = problemas de integridad, rechazo fuerte)
- El reporte para el editor solo se genera cuando el usuario lo pide explícitamente
- El idioma por defecto del reporte interno es español; el del editor es inglés (configurable)
- Las lecciones aprendidas se guardan en `~/.claude/scientific-reviewer/lessons_learned.md`, NO en el repo (están en .gitignore porque son personales)
