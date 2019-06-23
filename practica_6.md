# Parte 2: Lógica e inteligencia artificial.

## Práctica 1:

1. Traduzca al lenguaje simbólico los siguientes enunciados:

    1. Juan necesita un matemático o un informático.

        P = Juan necesita un matemático.  
        V = Juan necesita un informático.

        (P ⋁ Q)

    2. Si Juan necesita un informático entonces necesita un matemático.

        P = Juan necesita un informático.  
        Q = Juan necesita un matemático.

        (P → Q)

    3. Si Juan no necesita un matemático entonces necesita un informático.

        P = Juan necesita un matemático.  
        Q = Juan necesita un informático.

        (⌐P → Q)

    4. Si Juan contrata un informático entonces el proyecto tendrá éxito.

        P = Juan contrata un informático.  
        Q = El proyecto tiene éxito.

        (P → Q)

    5. Si el proyecto no tiene éxito entonces Juan no ha contratado un informático.

        P = El proyecto tiene éxito.  
        Q = Juan ha contratado un informático.

        (⌐P → ⌐Q)

    6. El proyecto tendrá éxito si y sólo si Juan contrata un informático.

        P = El proyecto tiene éxito.  
        Q = Juan contrata un informático.

        (P ↔ Q)

    7. Para aprobar Lógica, el alumno debe asistir a clase, desarrollar un cuaderno de prácticas aceptable y demostrar que dicho cuaderno ha sido desarrollado por él; o desarrollar un cuaderno de prácticas aceptable y aprobar el examen final.

        P = El alumno asiste a clase.
        Q = El alumno desarrolla un cuaderno de prácticas aceptable.
        R = El alumno demuestra que el cuaderno ha sido desarrollado por él.
        S = El alumno aprueba el examen final.
        T = El alumno aprueba Lógica.

        ((P ⋀ Q ⋀ R) ⋁ (Q ⋀ S)) → T

    8. El alumno puede asistir a clase u optar por un examen libre.

        P = El alumno asiste a clase.
        Q = El alumno opta por un examen libre.

        (P ⋀ Q)
    
    Seleccione de la lista anterior un par de enunciados que tengan la misma forma, y un par de enunciados que tengan el mismo significado.

        Los enunciados 2 y 4 tienen la misma forma.
        PREGUNTAR ENUNCIADOS MISMO SIGNIFICADO.

2. Se sabe que:

    * La página web tiene un error o el examen de álgebra no es el 2 de julio.
    * Si el examen de álgebra es el 2 de julio entonces la página web tiene un error.
    * El examen de álgebra es el 14 de julio si y sólo si la página web tiene un error y el período de exámenes no termina el 10 de julio.
    
    Teniendo en cuenta que el período de exámenes termina el 10 de julio y que la página web tiene un error, deducir la verdad o falsedad de los siguientes enunciados:
    
    1. El examen de álgebra es el 2 de julio.
    2. Si la página web no tiene un error entonces el examen de álgebra es el 14 de julio.
    
    _Idea: escríbalo como forma argumentativa y determine si es válida o inválida._

3. Se tienen las siguientes premisas:
    * Si Juan tiene suerte y llueve entonces estudia.
    * Juan aprobará si y sólo si estudia o tiene suerte.
    * Si Juan no tiene suerte entonces no llueve.

    Sabiendo que llueve, responder:
    1. ¿Aprobará Juan?
    2. ¿Tendrá suerte Juan?

    _Idea: escríbalo como forma argumentativa y determine si es válida o inválida_