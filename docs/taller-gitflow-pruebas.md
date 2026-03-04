# Documento de Pruebas

La Plataforma de Gestión de Eventos Universitarios es una solución de software diseñada para automatizar y controlar el ciclo de vida de la participación estudiantil en actividades académicas. El sistema centraliza el registro de usuarios bajo reglas de negocio específicas (edad y formato de código), valida la disponibilidad de cupos en tiempo real y garantiza la integridad de los datos mediante el control de inscripciones previas, asegurando una gestión eficiente y organizada de los eventos institucionales.

## 1. Descripcion del Sistema
La Plataforma de Gestión de Eventos Universitarios es una solución de software diseñada para automatizar y controlar el ciclo de vida de la participación estudiantil en actividades académicas. El sistema centraliza el registro de usuarios bajo reglas de negocio específicas (edad y formato de código), valida la disponibilidad de cupos en tiempo real y garantiza la integridad de los datos mediante el control de inscripciones previas, asegurando una gestión eficiente y organizada de los eventos institucionales.

La Plataforma de Gestión de Eventos Universitarios es una solución de software diseñada para automatizar y controlar el ciclo de vida de la participación estudiantil en actividades académicas. El sistema centraliza el registro de usuarios bajo reglas de negocio específicas (edad y formato de código), valida la disponibilidad de cupos en tiempo real y garantiza la integridad de los datos mediante el control de inscripciones previas, asegurando una gestión eficiente y organizada de los eventos institucionales.

## 2. Requerimientos a Evaluar
### **RF-01 Registro de Estudiante (Edad)**

El registro de estudiantes debe permitir lo siguiente:

-La edad debe estar entre los rangos **16** a **65** años 

### RF-02 Código de Estudiante

El código del estudiante debe:

- Tener exactamente 8 caracteres.
- Iniciar con la letra "E".
- Los 7 caracteres restantes deben ser numéricos.

### RF-03 Inscripción a Evento 

Un estudiante podrá inscribirse a un evento solo si:

-Está registrado.
-El evento tiene cupos disponibles.
-No está previamente inscrito.
Si alguna condición no se cumple, el sistema no debe permitir la inscripción.

## 3. Tecnicas de Prueba Aplicadas
##RF-01 La técnica que se llevara a cabo será la **Análisis de Valor Limite**, debido a que las posibles entradas tienen un rango numérico definido.

### RF-02 Código de Estudiante

**Técnica aplicada:** Partición de Equivalencia  

**Justificación:**  
El requerimiento establece reglas específicas de formato (longitud, carácter inicial y tipo de caracteres).  
La partición de equivalencia permite dividir los datos en clases válidas e inválidas para garantizar una cobertura adecuada de pruebas.
### **RF-01 Registro de Estudiante (Edad)**

### RF-03 Inscripción a Evento 

Tecnica de caja negra, tabla de decision

La tabla de decisión es la opción más adecuada porque permite representar claramente todas las combinaciones posibles de condiciones y sus resultados correspondientes, asegurando que funcione correctamente bajo diferentes escenarios.

## 4. Casos de Prueba Diseñados
## Casos de Prueba RF-01
| ID      |  Descripción                           | Entrada | Resultado Esperado                    | 
|---------|----------------------------------------|---------|---------------------------------------|
| CP-01   |  Dato a evaluar por debajo del rango   | 15      | Invalida, edad no dentro del rango    |
| CP-02   |  Dato a evaluar en el limite inferior  | 16      | Valida, edad dentro del rango         |
| CP-03   |  Dato a evaluar dentro del rango       | 40      | Valida, edad dentro del rango         |
| CP-04   |  Dato a evaluar en el limite superior  | 65      | Valida, edad dentro del rango         |
| CP-05   |  Dato a evaluar por encima del rango   | 90      | Invalida, edad no dentro del rango    |

### Casos de Prueba RF-02

| ID | Descripción | Entrada | Resultado Esperado |
|----|------------|----------|-------------------|
| ID-01 | Código válido | E1234567 | Registro exitoso |
| ID-02 | Menos de 8 caracteres | E123456 | Error: longitud inválida |
| ID-03 | Más de 8 caracteres | E12345678 | Error: longitud inválida |
| ID-04 | No inicia con E | A1234567 | Error: formato inválido |
| ID-05| Contiene letra en parte numérica | E1234A67 | Error: solo números permitidos |
| ID-06 | Contiene símbolo | E1234-67 | Error: formato inválido |

| ID Caso |  Descripción                          | Entrada |     Resultado Esperado                | 
|---------|---------------------------------------|---------|---------------------------------------|
| CP-06   |  Dato a evaluar por debajo del rango  | 15      | Invalida, edad no dentro del rango    |
| CP-07   |  Dato a evaluar en el limite inferior | 16      | Valida, edad dentro del rango         |
| CP-08   |  Dato a evaluar dentro del rango      | 40      | Valida, edad dentro del rango         |
| CP-09   |  Dato a evaluar en el limite superior | 65      |       Valida, edad dentro del rango   |
| CP-10   |  Dato a evaluar por encima del rango  | 90      | Invalida, edad no dentro del rango    |

## Casos de Prueba RF-03

| ID    | Condición/Combinación                             | Estudiante Registrado | Evento con Cupos | Estudiante Inscrito | Acción/Resultado Esperado          |
|-------|---------------------------------------------------|-----------------------|------------------|---------------------|------------------------------------|
| CP-11 | Estudiante Registrado, Evento con Cupos, No Inscrito   | Sí                    | Sí               | No                  | Permitir inscripción              |
| CP-12 | Estudiante No Registrado, Evento con Cupos, No Inscrito | No                    | Sí               | No                  | Denegar inscripción (No registrado) |
| CP-13 | Estudiante Registrado, Evento Sin Cupos, No Inscrito   | Sí                    | No               | No                  | Denegar inscripción (No hay cupos) |
| CP-14 | Estudiante Registrado, Evento con Cupos, Ya Inscrito   | Sí                    | Sí               | Sí                  | Denegar inscripción (Ya inscrito) |
| CP-15 | Estudiante No Registrado, Evento Sin Cupos, No Inscrito | No                    | No               | No                  | Denegar inscripción (No registrado / No cupos) |
| CP-16 | Estudiante Registrado, Evento Sin Cupos, Ya Inscrito   | Sí                    | No               | Sí                  | Denegar inscripción (No hay cupos) |

## 5. Trazabilidad

| Requerimiento | Técnica            | Casos Asociados |
|--------------|-------------------|------------------|
| RF-01       | Análisis de Valor Limite | CP-01, CP-02, CP-03, CP-04, CP-05 |
| RF-02       | Partición de Equivalencia | CP-06, CP-07, CP-08, CP-09, CP-10     |
| RF-03       | Tabla de Decision | CP-11, CP-12, CP-13, CP-14, CP-15, CP-16    |

## 6. Gestion de Versiones (GitFlow)

## Ramas creadas

Para la gestión del proyecto se utilizó una estrategia basada en GitFlow. Se crearon las siguientes ramas:

- **main**: Rama principal que contiene la versión estable y final del proyecto.
- **develop**: Rama de integración donde se consolidaron todos los desarrollos antes de pasar a producción.
- **feature/RF-01**: Implementación del Requerimiento Funcional 01.
- **feature/RF-02**: Implementación del Requerimiento Funcional 02.
- **feature/RF-03**: Implementación del Requerimiento Funcional 03.
- **feature/trazabilidad**: Desarrollo de la matriz de trazabilidad.

Cada requerimiento fue desarrollado en su propia rama `feature`, creada a partir de `develop`.

---

## Flujo seguido

El flujo de trabajo fue el siguiente:

1. Se trabajó sobre la rama `develop` como base de desarrollo.
2. Para cada requerimiento funcional se creó una rama `feature` desde `develop`.
3. Cada integrante desarrolló su requerimiento en su respectiva rama.
4. Al finalizar, se realizó un Pull Request hacia `develop`.
5. Una vez aprobado y fusionado, el siguiente integrante actualizaba su repositorio (`git pull`) para trabajar sobre la versión más reciente.
6. Finalmente, cuando todos los requerimientos estuvieron integrados y probados en `develop`, los cambios fueron fusionados hacia `main`.

Este flujo permitió mantener la estabilidad de `main`, dejando todos los cambios intermedios en `develop` hasta que el proyecto estuviera completo.

---

## Integración de cambios

La integración se realizó mediante Pull Requests desde cada rama `feature` hacia `develop`.

Antes de aprobar cada Pull Request:

- Se verificó el correcto funcionamiento del requerimiento.
- Se revisaron los cambios realizados.
- Se confirmó que no existieran errores o conflictos.

Una vez validados todos los requerimientos en `develop`, se realizó la fusión final hacia `main`.

---

## Conflictos y resolución

Debido a que el trabajo se realizó de manera secuencial (cada uno actualizaba el proyecto antes de comenzar su parte), los conflictos fueron mínimos.)

En caso de presentarse algún conflicto:

1. Git lo notificaba durante el proceso de merge.
2. Se revisaban manualmente las diferencias en el archivo afectado.
3. Se decidía qué cambios conservar.
4. Se realizaba un commit para finalizar la fusión.
