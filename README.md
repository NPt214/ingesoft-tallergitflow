# 📘 TALLER 2  
# GitFlow + Técnicas de Prueba de Caja Negra

---

## 🎯 Objetivo del Taller

Aplicar el modelo de ramas GitFlow (main, develop y feature) para gestionar cambios en documentación técnica, diseñando casos de prueba a partir del análisis de requerimientos utilizando técnicas de prueba de caja negra.

Este taller integra:

- Técnicas de prueba de caja negra
- Documentación en Markdown
- Gestión de configuración
- Control de versiones con GitFlow

---

## 👥 Organización del Trabajo

- Trabajo en grupos de **6 o 7 estudiantes**.
- Cada grupo trabajará en su propio repositorio.
- Se debe aplicar obligatoriamente GitFlow.
- No se permite trabajar directamente en `main`.

---

# 🏢 Sistema a Evaluar

**Plataforma de Gestión de Eventos Universitarios**

La plataforma permite:

1. Registro de estudiantes.
2. Validación de código estudiantil.
3. Inscripción a eventos.

---

# 📌 Requerimientos a Evaluar

---

## RF-01 Registro de Estudiante (Edad)

El sistema debe permitir el registro de estudiantes cuya edad esté entre 16 y 65 años inclusive.

---

## RF-02 Código de Estudiante

El código del estudiante debe:

- Tener exactamente 8 caracteres.
- Iniciar con la letra “E”.
- Los 7 caracteres restantes deben ser numéricos.

---

## RF-03 Inscripción a Evento

Un estudiante podrá inscribirse a un evento solo si:

- Está registrado.
- El evento tiene cupos disponibles.
- No está previamente inscrito.

Si alguna condición no se cumple, el sistema no debe permitir la inscripción.

---

# 🚀 PASO 0 – Línea Base Obligatoria (ANTES de GitFlow)

Antes de crear cualquier rama `develop` o `feature/*`, el grupo debe:

1. Crear la carpeta `docs/`.
2. Crear el archivo `docs/taller-giflow-pruebas.md`.
3. Agregar únicamente la estructura base del documento (sin desarrollar contenido).
4. Hacer commit en `main`.

### 📂 Estructura mínima inicial obligatoria:

```
# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

## 3. Tecnicas de Prueba Aplicadas

## 4. Casos de Prueba Diseñados

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
```

Commit sugerido:

```
docs(setup): crea estructura base del documento
```

⚠ Ninguna rama feature debe salir de un `main` vacío.

---

# 🌿 Implementación de GitFlow

## Paso 1
Crear la rama `develop` a partir de `main`.

---

## Paso 2
Cada integrante crea su rama desde `develop`:

```
feature/rf01-nombre
feature/rf02-nombre
feature/rf03-nombre
feature/trazabilidad-nombre
```

⚠ Las ramas feature deben salir de `develop`, NO de `main`.

---

# 👥 Distribución Interna del Grupo

---

### 👤 Personas 1 y 2 → RF-01

- Analizar el requerimiento.
- Determinar la técnica adecuada.
- Justificar brevemente la elección.
- Diseñar los casos de prueba.
- Validar cobertura.

---

### 👤 Personas 3 y 4 → RF-02

- Analizar el requerimiento.
- Determinar la técnica adecuada.
- Justificar la elección.
- Diseñar casos válidos e inválidos.
- Verificar cobertura.

---

### 👤 Personas 5 y 6 → RF-03

- Analizar condiciones.
- Determinar técnica adecuada.
- Justificar la elección.
- Diseñar combinaciones necesarias.
- Validar coherencia lógica.

---

### 👤 Persona 7 (si existe) → Trazabilidad e Integración

Responsable de:

- Crear tabla de trazabilidad.
- Verificar que cada RF tenga casos asociados.
- Revisar coherencia general.
- Coordinar integración en `develop`.
- Gestionar PR final hacia `main`.

---

# 🧠 Actividad Técnica

Para cada requerimiento deben:

1. Analizar el enunciado.
2. Determinar qué técnica de prueba de caja negra es la más adecuada.
3. Justificar brevemente la técnica seleccionada (máximo 3 líneas).
4. Diseñar los casos de prueba utilizando dicha técnica.
5. Documentar todo en Markdown.

Técnicas vistas en clase:

- Partición de equivalencia  
- Análisis de valor límite  
- Tabla de decisión  

⚠ No se debe aplicar la misma técnica a todos los requerimientos sin justificación.

---

# 📑 Desarrollo del Documento

---

## 1. Descripcion del Sistema

Breve descripción del sistema (máximo 5 líneas).

---

## 2. Requerimientos a Evaluar

Listar RF-01, RF-02 y RF-03.

---

## 3. Tecnicas de Prueba Aplicadas

Para cada RF incluir:

- Técnica seleccionada
- Justificación breve

---

## 4. Casos de Prueba Diseñados

Crear tablas correspondientes a cada RF.

---

## 5. Trazabilidad

| Requerimiento | Técnica | Casos Asociados |
|--------------|---------|----------------|
| RF-01 | (Técnica elegida) | CP-01, CP-02 |
| RF-02 | (Técnica elegida) | CP-03, CP-04 |
| RF-03 | (Técnica elegida) | CP-05, CP-06 |

---

## 6. Gestion de Versiones (GitFlow)

Describir:

- Ramas creadas.
- Flujo seguido.
- Cómo integraron cambios.
- Si hubo conflictos y cómo los resolvieron.

---

# 🔄 Integración Final

1. Cada feature debe hacer PR hacia `develop`.
2. Cuando todas estén integradas:
   - Revisar coherencia general.
   - Crear PR de `develop` hacia `main`.
   - Realizar merge final.

---

# 💬 Convención de Commits

Formato obligatorio:

```
tipo(area): descripcion clara en imperativo
```

Ejemplos:

```
docs(pruebas): agrega casos rf01
docs(pruebas): justifica tecnica rf02
docs(trazabilidad): agrega tabla de relacion
fix(pruebas): corrige tabla rf03
```

---

# 🎓 Reflexión Final

Responder en grupo:

1. ¿Qué técnica fue más compleja de identificar?
2. ¿Qué diferencia notaron entre develop y main?
3. ¿Qué pasaría si trabajaran directamente en main?
4. ¿Cómo ayuda GitFlow a controlar el cambio?

---

La gestión del cambio no evita errores.  
Los hace controlables.
