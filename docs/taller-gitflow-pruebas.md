# Documento de Pruebas

## 1. Descripcion del Sistema

## 2. Requerimientos a Evaluar
    R03

## 3. Tecnicas de Prueba Aplicadas
    Tecnica de caja negra, tabla de decision

    La tabla de decisión es la opción más adecuada porque permite representar claramente todas las combinaciones posibles de condiciones y sus resultados correspondientes, asegurando que funcione correctamente bajo diferentes escenarios.
## 4. Casos de Prueba Diseñados
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