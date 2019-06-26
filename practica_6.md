# Parte 2: Lógica e inteligencia artificial.

## Práctica 1:

1. Traduzca al lenguaje simbólico los siguientes enunciados:

    1. Juan necesita un matemático o un informático.

        p = Juan necesita un matemático.  
        V = Juan necesita un informático.

        (p ⋁ q)

    2. Si Juan necesita un informático entonces necesita un matemático.

        p = Juan necesita un informático.  
        q = Juan necesita un matemático.

        (p → q)

    3. Si Juan no necesita un matemático entonces necesita un informático.

        p = Juan necesita un matemático.  
        q = Juan necesita un informático.

        (⌐p → q)

    4. Si Juan contrata un informático entonces el proyecto tendrá éxito.

        p = Juan contrata un informático.  
        q = El proyecto tiene éxito.

        (p → q)

    5. Si el proyecto no tiene éxito entonces Juan no ha contratado un informático.

        p = El proyecto tiene éxito.  
        q = Juan ha contratado un informático.

        (⌐p → ⌐q)

    6. El proyecto tendrá éxito si y sólo si Juan contrata un informático.

        p = El proyecto tiene éxito.  
        q = Juan contrata un informático.

        (p ↔ q)

    7. Para aprobar Lógica, el alumno debe asistir a clase, desarrollar un cuaderno de prácticas aceptable y demostrar que dicho cuaderno ha sido desarrollado por él; o desarrollar un cuaderno de prácticas aceptable y aprobar el examen final.

        p = El alumno asiste a clase.  
        q = El alumno desarrolla un cuaderno de prácticas aceptable.  
        r = El alumno demuestra que el cuaderno ha sido desarrollado por él.  
        s = El alumno aprueba el examen final.  
        t = El alumno aprueba Lógica.

        ((p ⋀ q ⋀ r) ⋁ (q ⋀ s)) → t

    8. El alumno puede asistir a clase u optar por un examen libre.

        p = El alumno asiste a clase.  
        q = El alumno opta por un examen libre.

        (p ⋁ q)
    
    Seleccione de la lista anterior un par de enunciados que tengan la misma forma, y un par de enunciados que tengan el mismo significado.

    Los enunciados 2 y 4 tienen la misma forma. Los enunciados 4 y 5, el mismo significado.

2. Se sabe que:

    * La página web tiene un error o el examen de álgebra no es el 2 de julio.
    * Si el examen de álgebra es el 2 de julio entonces la página web tiene un error.
    * El examen de álgebra es el 14 de julio si y sólo si la página web tiene un error y el período de exámenes no termina el 10 de julio.
    
    Teniendo en cuenta que el período de exámenes termina el 10 de julio y que la página web tiene un error, deducir la verdad o falsedad de los siguientes enunciados:
    
    1. El examen de álgebra es el 2 de julio.
    2. Si la página web no tiene un error entonces el examen de álgebra es el 14 de julio.
    
    _Idea: escríbalo como forma argumentativa y determine si es válida o inválida._

    Primero considero las siguientes variables:

    p = La página web tiene un error.  
    q = El examen de álgebra es el 2 de julio.  
    r = El examen de álgebra es el 14 de julio.  
    s = El período de exámenes termina el 10 de julio.

    Paso a construir los enunciados:

    * La página web tiene un error o el examen de álgebra no es el 2 de julio.

        (p ⋁ ⌐q)

    * Si el examen de álgebra es el 2 de julio entonces la página web tiene un error.

        (q → p)

    * El examen de álgebra es el 14 de julio si y sólo si la página web tiene un error y el período de exámenes no termina el 10 de julio.

        (r ↔ (p ⋀ ⌐s))

    Paso a redactar los enunciados como formas argumentativas, teniendo en cuenta que s y p son verdaderos:

    (p ⋁ ⌐q), (q → p), (r ↔ (p ⋀ ⌐s)) ∴ q

    Jugando con los valores de verdad, dado p verdadero, si q fuera falsa, por ejemplo, se puede observar que los dos primeros enunciados son verdaderos. Para el tercer enunciado suponiendo s verdadero, por el complemento queda falso. P ya era verdadero así es que esa conjunción queda falsa. Asumo que r es falso para lograr que ese bincondicional sea verdadero y así poder mostrar que dados los enunciados verdaderos, la conclusión es falsa.

    (p | ⋁ | ⌐q | (q | → | p) | (r | ↔ | (p | ⋀ | ⌐s)) | ∴ | q
    :---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
    V(ya se daba por defecto) | V | V(puse F, pero por el complemento cambió a V) | F(Ponga lo que ponga me va a dar verdadero) | V | V(ya se daba por defecto) | F(la única manera de que el bicondicional de verdadero)| V | V(ya se daba por defecto.)| F(es el único valor que podía darse) | F(era V pero cambia a F por el complemento. Ya se da por defecto.) | F | F(es el valor que le había asignado a q)

    (p ⋁ ⌐q), (q → p), (r ↔ (p ⋀ ⌐s)) ∴ (⌐p → r)

    Siguiendo el razonamiento de arriba se puede concluir que el valor de r es el único posible para asegurar que el enunciado 3 sea verdadero. Así mismo, el valor para p ya viene dado, por lo que el argumento es válido.

    (p | ⋁ | ⌐q) | (q | → | p) | (r | ↔ | (p | ⋀ | ⌐s)) | ∴ | (⌐p | → |r)
    :---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
    V(ya se daba por defecto)| V | V(puse F, pero por el complemento cambió a V)| F(Ponga lo que ponga me va a dar verdadero) | V |V(ya se daba por defecto)| F(la única manera de que el bicondicional de verdadero)| V |V(ya se daba por defecto)|F(es el único valor que podía darse)|F(era V pero cambia a F por el complemento. Ya se da por defecto.)| V |F(era V pero cambia a F por el complemento. Ya se da por defecto.)| V |F(es el único valor que puedo poner en r para garantizar que los enunciados sean verdaderos)

3. Se tienen las siguientes premisas:

    * Si Juan tiene suerte y llueve entonces estudia.
    * Juan aprobará si y sólo si estudia o tiene suerte.
    * Si Juan no tiene suerte entonces no llueve.

    Sabiendo que llueve, responder:

    1. ¿Aprobará Juan?
    2. ¿Tendrá suerte Juan?

    _Idea: escríbalo como forma argumentativa y determine si es válida o inválida_

    Idem el punto anterior. Primero declaro las variables:

    p = Juan tiene suerte  
    q = Llueve.  
    r = Juan aprueba.  
    s = Juan estudia.  

    Luego convierto a símbolos cada enunciado:

    * Si Juan tiene suerte y llueve entonces estudia.

        ((p ⋀ q) → s)

    * Juan aprobará si y sólo si estudia o tiene suerte.

        (r ↔ (s ⋁ p))

    * Si Juan no tiene suerte entonces no llueve.

        (⌐p → ⌐q)

    Finalmente armo la forma argumentativa y la resuelvo:

    ((p ⋀ q) → s), (r ↔ (s ⋁ p)), (⌐p → ⌐q) ∴ r

    Jugando con los valores de verdad, a priori, teniendo que q es verdadero, en el último enunciado cambia a falso por el complemento. Esto hace que el único valor que pueda tomar p para que la implicación sea verdadera es F, pero, como hay una operación de complemento, voy a elegir V. Esto hace que la conjunción del primer enunciado me quede verdadera(tanto p como q son verdaderos), solo resta elegir s, que, como la operación es una implicación, el único valor posible para que ésta sea verdadera es V. Definiendo s completo la disyunción del segundo enunciado que también da verdadero, ya que en este caso, tanto s como p son verdaderos. Solo resta elegir el valor de r para que se cumpla el bicondicional. Al ser verdadera una de las partes, la otra también necesariamente debe serlo para que de verdadero, por lo que r queda como verdadero y se cumple que es un argumento válido.

    ((p | ⋀ | q) | → | s) | (r | ↔ | (s | ⋁ | p)) | (⌐p | → | ⌐q) | ∴ | r
    :---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
    V|V|V|V|V|V|V|V|V|V|F|V|F|V|V

    ((p ⋀ q) → s), (r ↔ (s ⋁ p)), (⌐p → ⌐q) ∴ p

    Siguiendo el razonamiento anterior, también se puede probar con eso que el único valor posible para p es verdadero y que, por ende, el argumento es válido.

    ((p | ⋀ | q) | → | s) | (r | ↔ | (s | ⋁ | p)) | (⌐p | → | ⌐q) | ∴ | p
    :---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
    V|V|V|V|V|V|V|V|V|V|F|V|F|V|V