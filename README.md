# Sistema de Coaching de Alemán (6 semanas)

Este repositorio contiene un plan completo para aprender alemán desde nivel inicial (`A0`) hasta un nivel inicial funcional (`A1 temprano`), con foco en mudanza a Alemania y comunicación cotidiana/laboral.

## Estructura

- `00-assessment/`: diagnóstico inicial y rúbrica de decisión de nivel.
- `01-syllabus/`: plan de 6 semanas con 7 días por semana.
- `02-sessions/`: plantillas de sesiones (autoestudio y sesión guiada) y checklist de pronunciación.
- `03-tracking/`: seguimiento diario/semanal y registro de errores fosilizados.
- `04-materials/`: materiales ejecutables de autoestudio por día (input, ejercicios, producción, clave).

## Cómo usar este sistema

1. Ejecuta primero `00-assessment/placement-test.md`.
2. Corrige con `00-assessment/placement-answer-key.md`.
3. Determina nivel en `00-assessment/level-decision-rubric.md`.
4. Revisa `01-syllabus/overview-6-weeks.md` y el archivo de semana correspondiente.
5. Cada día:
   - Ella realiza `90 min` de autoestudio usando el material diario en `04-materials/...`.
   - Ustedes hacen `30 min` juntos (`15 min` contenido nuevo + `15 min` repaso/corrección).
   - Registran resultados en `03-tracking/learning-log.md`.
6. Cada semana, completar `03-tracking/weekly-review-template.md` y actualizar `03-tracking/issue-log-fossil-errors.md`.

## Estado actual de materiales

- Week 1 ya tiene pack completo en `04-materials/week-01/day-01.md` a `day-07.md`.
- Cada día de `01-syllabus/week-01.md` incluye enlace directo a su material de autoestudio.
- Si una semana no tiene material ejecutable aún, generarlo antes de iniciar ese día.

## Web local (Markdown como páginas)

El repo está preparado para visualizar cada `.md` como página web separada usando Docsify.

Archivos de soporte:
- `index.html`: arranque de Docsify.
- `_sidebar.md`: navegación por materiales.

Arranque recomendado en Ubuntu/EC2:
```bash
npm install -g docsify-cli
cd /home/mpuels/projects/carolina-curso-aleman
docsify serve . -p 8080
```

Ejemplo de página diaria:
- `http://<EC2_PUBLIC_IP>:8080/#/04-materials/week-01/day-01`

Nota audio:
- En `04-materials/week-01/day-01.md` ya hay un reproductor `<audio controls>` por turno del diálogo, enlazado a `05-audio/week-01/day-01/*.mp3`.

## Reglas operativas

- Mantener ritmo de `7 días/semana` durante `6 semanas`.
- No introducir más de `1` patrón nuevo principal al día.
- En pronunciación, corregir solo `1-2` objetivos diarios.
- El repaso diario siempre parte de errores del día anterior.

## Criterio de éxito al final de 6 semanas

- Mantener una conversación básica de 3-5 minutos en contextos reales (casa, compras, transporte, trabajo básico).
- Comprender instrucciones frecuentes y preguntas cotidianas.
- Completar tareas prácticas de mudanza (citas, datos personales, formularios simples) con apoyo mínimo.
