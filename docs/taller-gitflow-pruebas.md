# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar
### RF-02 Código de Estudiante

El código del estudiante debe:

- Tener exactamente 8 caracteres.
- Iniciar con la letra "E".
- Los 7 caracteres restantes deben ser numéricos.

## 3. Tecnicas de Prueba Aplicadas
### RF-02 Código de Estudiante

**Técnica aplicada:** Partición de Equivalencia  

**Justificación:**  
El requerimiento establece reglas específicas de formato (longitud, carácter inicial y tipo de caracteres).  
La partición de equivalencia permite dividir los datos en clases válidas e inválidas para garantizar una cobertura adecuada de pruebas.

## 4. Casos de Prueba Diseñados
### Casos de Prueba RF-02

| ID | Descripción | Entrada | Resultado Esperado |
|----|------------|----------|-------------------|
| CP-03 | Código válido | E1234567 | Registro exitoso |
| CP-04 | Menos de 8 caracteres | E123456 | Error: longitud inválida |
| CP-05 | Más de 8 caracteres | E12345678 | Error: longitud inválida |
| CP-06 | No inicia con E | A1234567 | Error: formato inválido |
| CP-07 | Contiene letra en parte numérica | E1234A67 | Error: solo números permitidos |
| CP-08 | Contiene símbolo | E1234-67 | Error: formato inválido |

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
