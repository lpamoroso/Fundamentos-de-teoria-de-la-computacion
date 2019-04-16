# Reducciones de problemas. MT restringidas

1. Considerando la reducción de HP a Lᵤ descripta en clase, responder:
    1. Explicar por qué la función identidad, es decir la función que a toda cadena le asigna la misma cadena, no es una reducción de HP a Lᵤ.

        //PREGUNTAR. PORQUE, PARA MI, LO QUE SE BUSCA ES OTRA COSA. DEFINIENDO F((<M>, W)) = F((<M\`>, W)), SI BIEN M Y M\` SON IDÉNTICAS, LA DIFERENCIA ESTÁ EN QUE LOS Qᵣ DE M SON LOS Qₐ DE M\`.

    2. Explicar por qué las MT M\` generadas en los pares (<M\`>, w) de Lᵤ, o bien paran aceptando, o bien loopean.

        //PREGUNTAR. PORQUE SI M PARA SOBRE W, M\` ACEPTA W PORQUE NO TIENE Qᵣ Y SI M NO PARA SOBRE W, TAMPOCO LO HACE M`.

    3. Explicar por qué la función utilizada para reducir HP a Lᵤ también sirve para reducir HPᶜ a Lᵤᶜ.

        //PREGUNTAR(SI NO ESTÁ BIEN, PONGO LA DEFINICIÓN DE REDUCCIÓN). PORQUE HAY UNA PROPIEDAD DE REDUCCIONES QUE DICE QUE L₁ α L₂ ↔ HPᶜ a Lᵤᶜ.

    4. Explicar por qué la función utilizada para reducir HP a Lᵤ no sirve para reducir Lᵤ a HP.
    5. Explicar por qué si el input v de la MT M<sub>f</sub> que computa la función de reducción no tiene la forma (<M>, w), no es correcto que M<sub>f</sub> genere, en lugar de la cadena 1, un par de la forma (<M<sub>Ʃ*</sub>>, v), siendo M<sub>Ʃ*</sub> una MT que acepta todas las cadenas.
    6. Explicar por qué la siguiente MT M<sub>f</sub> no computa una reducción de HP a Lᵤ: dado v:
        * Si v no tiene la forma (<M>, w), entonces M<sub>f</sub> genera el output 1.
        * Si v tiene la forma (<M>,w), entonces M<sub>f</sub> ejecuta M sobre w, y, si M acepta w, entonces genera el output (<M>,w); y, si M rechaza w, entonces genera el output 1.

2. Probar el caso (b) del teorema presentado en clase, que enuncia:
    * Caso (a): Si L1 α L2 entonces L2 ∈ R ⟶ L1 ∈ R.
    * Caso (b): Si L1 α L2 entonces L2 ∈ RE ⟶ L1 ∈ RE.

    *Ayuda: basarse en la demostración del caso (a) desarrollada en clase.*

3. Considerando la reducción de Lᵤ a L<sub>Ʃ*</sub> descripta en clase, responder:
    1. Explicar por qué no sirve como función de reducción la función siguiente: a todo input le asigna como output el código <M<sub>Ʃ*</sub>>.
    2. Explicar por qué la reducción descripta en clase no sirve para probar que L<sub>Ʃ*</sub> ∉ RE.

4. Probar formalmente que las funciones de reducción gozan de la propiedad transitiva.
*Ayuda: revisar la idea general comentada en clase; también basarse en la prueba que se haya desarrollado para el 2, porque debería ser similar.*

5. Sea el lenguaje Dₕₚ = {wᵢ | Mipara desde wᵢ, según el orden canónico}. Encontrar una reducción de Dₕₚ a HP.

6. Sea el lenguaje L<sub>∅</sub> = {<M>| L(M) = ∅}. Responder:
    1. Encontrar una reducción de Lᵤᶜ a L<sub>∅</sub>.  
    *Ayuda: basarse en la idea de la reducción de Lᵤ a L<sub>Ʃ*</sub>, es muy similar.*
    2. Considerando la reducción desarrollada en (1) ¿Qué se puede decir de L<sub>∅</sub>, a qué clase de la jerarquía de la computabilidad pertenece?

7. Construir un autómata finito que reconozca el lenguaje de las cadenas de {0, 1}*, es decir todas las cadenas de 0 y 1 de cualquier tamaño incluso la vacía, tales que a todo cero le siga un uno.  
*Ayuda: En general conviene primero construir el diagrama de transición de estados, porque da una idea de cómo construir el autómata finito.*

8. Un autómata linealmente acotado(ALA) es una MT con una sola cinta con la restricción de que su cabezal sólo puede leer y escribir en las celdas en que se encuentra el input. Probar que el lenguaje aceptado por un ALA es recursivo.

*Ayuda: ¿En cuántos pasos se puede detectar que el ALA entra en loop?*