# Documento de Pruebas

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
##Casos de Prueba RF-01
| ID Caso |  Descripción   |    Entrada     |              Resultado Esperado                 | 


|---------|----------------|----------------|-------------------|-----------------------------|


| CP-01 |  Dato a evaluar por debajo del rango   | 15 | Invalida, edad no dentro del rango |


| CP-02 |  Dato a evaluar en el limite inferior  | 16 | Valida, edad dentro del rango |


| CP-03 |  Dato a evaluar dentro del rango       | 40 | Valida, edad dentro del rango |


| CP-04 |  Dato a evaluar en el limite superior  | 65 | Valida, edad dentro del rango |


| CP-05 |  Dato a evaluar por encima del rango   | 90 | Invalida, edad no dentro del rango |


|---------|----------------|----------------|-------------------|-----------------------------|

### Casos de Prueba RF-02

| ID | Descripción | Entrada | Resultado Esperado |
|----|------------|----------|-------------------|
| CP-03 | Código válido | E1234567 | Registro exitoso |
| CP-04 | Menos de 8 caracteres | E123456 | Error: longitud inválida |
| CP-05 | Más de 8 caracteres | E12345678 | Error: longitud inválida |
| CP-06 | No inicia con E | A1234567 | Error: formato inválido |
| CP-07 | Contiene letra en parte numérica | E1234A67 | Error: solo números permitidos |
| CP-08 | Contiene símbolo | E1234-67 | Error: formato inválido |

| ID Caso |  Descripción   |    Entrada     |              Resultado Esperado                 | 


|---------|----------------|----------------|-------------------|-----------------------------|


| CP-01 |  Dato a evaluar por debajo del rango   | 15 | Invalida, edad no dentro del rango |


| CP-02 |  Dato a evaluar en el limite inferior  | 16 | Valida, edad dentro del rango |


| CP-03 |  Dato a evaluar dentro del rango       | 40 | Valida, edad dentro del rango |


| CP-04 |  Dato a evaluar en el limite superior  | 65 | Valida, edad dentro del rango |


| CP-05 |  Dato a evaluar por encima del rango   | 90 | Invalida, edad no dentro del rango |


|---------|----------------|----------------|-------------------|-----------------------------|

##Casos de Prueba RF-03

| ID    | Condición/Combinación                             | Estudiante Registrado | Evento con Cupos | Estudiante Inscrito | Acción/Resultado Esperado          |
|-------|---------------------------------------------------|-----------------------|------------------|---------------------|------------------------------------|
| cp-09 | Estudiante Registrado, Evento con Cupos, No Inscrito   | Sí                    | Sí               | No                  | Permitir inscripción              |
| cp-10 | Estudiante No Registrado, Evento con Cupos, No Inscrito | No                    | Sí               | No                  | Denegar inscripción (No registrado) |
| cp-11 | Estudiante Registrado, Evento Sin Cupos, No Inscrito   | Sí                    | No               | No                  | Denegar inscripción (No hay cupos) |
| cp-12 | Estudiante Registrado, Evento con Cupos, Ya Inscrito   | Sí                    | Sí               | Sí                  | Denegar inscripción (Ya inscrito) |
| cp-13 | Estudiante No Registrado, Evento Sin Cupos, No Inscrito | No                    | No               | No                  | Denegar inscripción (No registrado / No cupos) |
| cp-14 | Estudiante Registrado, Evento Sin Cupos, Ya Inscrito   | Sí                    | No               | Sí                  | Denegar inscripción (No hay cupos) |

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
