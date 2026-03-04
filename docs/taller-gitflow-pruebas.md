# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar

### **RF-01 Registro de Estudiante (Edad)**

El registro de estudiantes debe permitir lo siguiente:

-La edad debe estar entre los rangos **16** a **65** años 

### 3. Tecnicas de Prueba Aplicadas

La técnica que se llevara a cabo será la **Análisis de Valor Limite**, debido a que las posibles entradas tienen un rango numérico definido.

## 4. Casos de Prueba Diseñados

| ID Caso |  Descripción   |    Entrada     |              Resultado Esperado                 | 
|---------|----------------|----------------|-------------------|-----------------------------|
| CP-01 |  Dato a evaluar por debajo del rango   | 15 | Invalida, edad no dentro del rango |
| CP-02 |  Dato a evaluar en el limite inferior  | 16 | Valida, edad dentro del rango |
| CP-03 |  Dato a evaluar dentro del rango       | 40 | Valida, edad dentro del rango |
| CP-04 |  Dato a evaluar en el limite superior  | 65 | Valida, edad dentro del rango |
| CP-05 |  Dato a evaluar por encima del rango   | 90 | Invalida, edad no dentro del rango |
|---------|----------------|----------------|-------------------|-----------------------------|

## 5. Trazabilidad

## 6. Gestion de Versiones (GitFlow)
