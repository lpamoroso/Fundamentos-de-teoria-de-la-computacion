# Práctica 1

1. Responder brevemente los siguientes incisos:

    1. ¿Qué es un problema(computacional) de decisión? ¿Es el tipo de problema más general que se puede formular?

        Un problema computacional de decisión es aquel para el que existe una máquina de turing que responde SI o NO. Los problemas más generales son los problemas de búsqueda.

    2. ¿Qué cadenas forman el lenguaje aceptado por una MT?

        Todas las cadenas que acepte la máquina de turing.

    3. En la clase 1 se hace referencia al problema de satisfactibilidad de las fórmulas booleanas(se da como ejemplo la fórmula φ=(x1∨x2)∧(x3∧x4) y la asignación A=(V,F,V,V)). Formular las tres formas del problema, teniendo en cuenta las tres visiones de MT consideradas: calculadora, aceptadora o reconocedora y generadora.

        Si se utilizare una máquina calculadora, entonces se devolverá alguno de los resultados de aplicar un input sobre la máquina. Si en cambio, se utiliza una máquina aceptadora, entonces lo que se devolverá es si el lenguaje provista acepta o no. Con la máquina generadora, por su parte, se devolveran todas las soluciones al lenguaje provisto.

    4. ¿Qué postula la Tesis de Church-Turing?

        Postula que todo lo computable puede ser llevado a cabo con una máquina de turing.

    5. ¿Cuándo dos MT son equivalentes? ¿Cuándo dos modelos de MT son equivalentes?

        Dos modelos de MT son equivalentes cuando para toda MT M1 de un modelo existe una MT M2 equivalente del otros, es decir que L(M1)=L(M2).

2. Dado el alfabeto Ʃ = {a, b, c}:
    1. Obtener el lenguaje Ʃ* y el conjunto de partes del subconjunto de Ʃ* con cadenas de a lo sumo dos símbolos. ¿Cuál es el cardinal (o tamaño) de este último conjunto?

    Ʃ* = {&lambda;, a, b, c, aa, ab, ac, ba, bb, bc, ca, cb, cc}
    P(Ʃ*) = {{ }, {a}, {b}, {a,b}, {b,c}, ...}

    En total hay 2^13 elementos.

    2. Dado el lenguaje L = {aⁿbⁿcⁿ | n ≥ 0}, obtener la intersección Ʃ* ⋂ L, la unión Ʃ* ⋃ L, el complemento de L respecto de Ʃ*, y la concatenación Ʃ . L.

    Intersección = L.
    Unión = Ʃ*.
    Complemento = {a, b, c, ab, ac, ...}(Cualquier string que no esté en L).
    Concatenación = Ʃ*.
 
3. Completar la prueba iniciada en la clase 1, de que L(M) = {aⁿbⁿ | n ≥ 1}, siendo M la MT construida para aceptar dicho lenguaje.

    Si w empieza con a, entonces convierte el caracter en α y se mueve a la derecha. Si luego detecta un B, se detiene. Mientras hayan a o β, la máquina se mueve a la derecha. Cuando llega a b, lo convierte en β y se mueve a la izquierda. De nuevo, si encuentra un B, se detiene. Mientras hayan a o β, la máquina se mueve a la izquierda. Si encuentra un α, significa que se pasó, avanza a la derecha y vuelve a proceder como al principio para seguir procesando la cadena. Cuando haya terminado de procesar las a y se choque con un β, eso significa que terminó de procesar las a, por lo que se mueve a la derecha tantas veces como β haya y, al encontrar un B, se detiene.

4. En la clase 1 se construyó una MTN (MT no determinística) para aceptar las cadenas de la forma haⁿ o hbⁿ, con n ≥ 0. Construir ahora una MTD (MT determinística) para lo mismo.

    Habría que dividir la cinta en tracks, en la que cada track tenga la cadena correspondiente a analizar e ir procesando una parte de cada cadena.

5. En la clase 1 se construyó una MT con dos cintas para aceptar el lenguaje L = {w | w ∈ {a, b}* y w es un palíndromo o “capicúa”}. Construir ahora una MT con una cinta para aceptar el mismo lenguaje (se puede considerar la idea de solución propuesta en clase).

    Idea general: la propiedad de las palabras capicúas es que pueden leerse de manera igual al derecho y al revés, por lo que la idea será, por ejemplo, si la cadena empieza con a, marcarla, moverse a la derecha hasta el final y ver si se encuentra la a. Así con cada caracter.
    Construcción: la correspondiente MT M = (Q, Ʃ, Γ, δ, q0, qA, qR) en donde Q = {q0, qa, qb, qL, qH}. q0 representa el estado inicial en el que se detecta una a o una b. En q1, habiendose detectado una a se va hasta el último caracter procesado(un B, α o β) y, cuando llega a alguno de esos, va un paso a la izquierda porque ya se pasó. En q2, si detecta una a, la convierte en α y se dirije a la izquierda hasta encontrar una a o una b. Si encuentra un B se detiene. q3, q4 y q5 representan el camino análogo pero suponiendo que se encuentra una b y debe ser procesada como tal.
    Ʃ = {a, b}, Γ = {a, b, α, β, B}.
 
6. Se pretende construir una MT(puede tener varias cintas) que acepte de la manera más eficiente posible el lenguaje L = {aⁿbⁿcⁿ | n ≥ 0}. Plantear la idea general de la MT (opcionalmente construirla formalmente).

    ### Idea general

    En este caso, lo que conviene es usar varias cintas ya que se podría contar las a en una de las cintas, las b en otra y la c en la cinta restante, y luego comparar las ocurrencias si son iguales.
 
7. Construir una MT que calcule la resta de dos números (se puede considerar la idea de solución propuesta en la clase 1).

    ### Idea general
    En este caso, yo tendría 3 cintas: una para el minuendo, otra para el sustraendo y una última para la diferencia. La idea sería tomar el caracter de la primera cinta y restarlo con el caracter de la segunda y setear el resultado en la tercera. Luego avanzar todas las cintas hacia la derecha y repetir los pasos hasta llegar a blanco(es decir que no hay más caracteres que restar).

8. Construir una MT que genere todas las cadenas de la forma aⁿbⁿ, con n ≥ 1 (se puede considerar la idea de solución propuesta en la clase 1).

    ### Idea general
    Lo que podría hacerse es arrancar seteando a y luego b. Luego, cuando se avanza a la derecha, se encontrará un B: hay que transformarlo en b e ir a la izquierda lo más que se pueda si modificar nada hasta volver a encontrar un B, pero, esta vez, se transformará el B en a y se irá a la derecha todo lo que se pueda hasta volver a encontrar un B y repetir la secuencia,.
 
9. Explicar (informal pero claramente) cómo simular una MT por otra que en un paso no pueda simultáneamente modificar un símbolo y moverse.

    Si en un mismo paso no puede, simultáneamente, modificar un símbolo y moverse, entonces tendrá que hacerlo en diferentes pasos, es decir, en un paso modificará el símbolo y se quedará quieto y en el siguiente se moverá a la derecha o a la izquierda sin alterar nada.
 
10. Explicar (informal pero claramente) cómo simular una MT por otra que no tenga el movimiento S (es decir el no movimiento).

    Si la MT no sabe cómo quedarse quieta, esto podrá simularse avanzando a la derecha en un paso y luego a la izquierda en el otro o viceversa.
 
11. Explicar (informal pero claramente) cómo simular una MT por otra que no tenga el movimiento L sino JUMP, que posiciona el cabezal en el símbolo de más a la izquierda. 

    Si la MT, en lugar de ir a la izquierda, va al extremo izquierdo, lo que yo haría es referenciar de alguna manera(un caracter especial, por ejemplo) al lugar en donde estaba antes de ir al principio de la cinta. Entonces, cuando vuelva al principio y empiece a avanzar, reconocerá el caracter especial y actuará en consecuencia.
 
12. Justificar por qué la siguiente MTN M acepta el lenguaje de las fórmulas booleanas satisfactibles. Dada una fórmula booleana Φ, M hace:

    1. Si Φ no es correcta sintácticamente, rechaza.
    2. Genera no determinísticamente una asignación de valores de verdad A.
    3. Acepta si y sólo si A satisface Φ.  
    *Comentario: notar que el no determinismo de M se refleja en el paso 2. El paso 2 constituye una bifurcación de varias computaciones, en cada una se genera una asignación posible de valores de verdad. El conjunto de todas estas computaciones reúne a todas las posibles asignaciones.*

    Para mí, acepta el lenguaje de la fórmulas booleanas satisfactibles ya que con el primer paso filtra las fórmulas que no sean sintácticamente correctas. Luego revisa la semántica, generando, de forma no determinística, múltiples flujos. Si alguno de los flujos acepta, la máquina acepta.