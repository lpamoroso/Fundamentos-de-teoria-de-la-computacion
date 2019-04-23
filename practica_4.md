# Reducciones de problemas. MT restringidas

1. Considerando la reducción de HP a Lᵤ descripta en clase, responder:
    1. Explicar por qué la función identidad, es decir la función que a toda cadena le asigna la misma cadena, no es una reducción de HP a Lᵤ.

        Porque, si bien no hay problema para el caso en que acepta o que es una cadena inválida, cuando se da qᵣ en HP, se va a dar qₐ en Lᵤ, por lo que no se logra que si un elemento está en HP, esté también en Lᵤ.

    2. Explicar por qué las MT M\` generadas en los pares (<M\`>, w) de Lᵤ, o bien paran aceptando, o bien loopean.

        //PREGUNTAR. PORQUE SI M PARA SOBRE W, M\` ACEPTA W PORQUE NO TIENE Qᵣ Y SI M NO PARA SOBRE W, TAMPOCO LO HACE M`.

    3. Explicar por qué la función utilizada para reducir HP a Lᵤ también sirve para reducir HPᶜ a Lᵤᶜ.

        //PREGUNTAR(SI NO ESTÁ BIEN, PONGO LA DEFINICIÓN DE REDUCCIÓN). PORQUE HAY UNA PROPIEDAD DE REDUCCIONES QUE DICE QUE L₁ α L₂ ↔ HPᶜ a Lᵤᶜ.

    4. Explicar por qué la función utilizada para reducir HP a Lᵤ no sirve para reducir Lᵤ a HP.

        Porque la propiedad de simetría no se cumple en reducciones, es decir, sea L ∈ R, se da que L α Lᵤ, pero esto no implica que Lᵤ α L, ya que eso supondría que L es "tan o más dificil" que Lᵤ, y lo cierto es que Lᵤ ∉ R, por lo que claramente Lᵤ es más dificil que L.

    5. Explicar por qué si el input v de la MT M<sub>f</sub> que computa la función de reducción no tiene la forma (<M>, w), no es correcto que M<sub>f</sub> genere, en lugar de la cadena 1, un par de la forma (<M<sub>Ʃ*</sub>>, v), siendo M<sub>Ʃ*</sub> una MT que acepta todas las cadenas.

        //NO ENTIENDO MUY BIEN LO QUE DICE, PERO, A PRIORI, SE ME OCURRE QUE NO ESTARÍA BIEN PORQUE LA IDEA ERA QUE M\` ACEPTARA W SOLO CUANDO M PARARA SOBRE W, Y EN CASO DE QUE M NO PARARA SOBRE W, TAMPOCO PARARÍA M\`. M<sub>Ʃ*</sub> ES una MT que acepta todas las cadenas, NO ES LO QUE SE BUSCA.

    6. Explicar por qué la siguiente MT M<sub>f</sub> no computa una reducción de HP a Lᵤ dado v:
        * Si v no tiene la forma (<M>, w), entonces M<sub>f</sub> genera el output 1.
        * Si v tiene la forma (<M>,w), entonces M<sub>f</sub> ejecuta M sobre w, y, si M acepta w, entonces genera el output (<M>,w); y, si M rechaza w, entonces genera el output 1.

        No computa dado que si la entrada es una cadena válida, para generar <M`>, M<sub>f</sub> debe modificar las 5-tuplas de <M> reemplazando todo estado Qᵣ por Qₐ.

2. Probar el caso (b) del teorema presentado en clase, que enuncia:
    * Caso (a): Si L₁ α L₂ entonces L₂ ∈ R ⟶ L₁ ∈ R.
    * Caso (b): Si L₁ α L₂ entonces L₂ ∈ RE ⟶ L₁ ∈ RE.

    *Ayuda: basarse en la demostración del caso (a) desarrollada en clase.*

    La idea general es que si existe una MT M<sub>f</sub> que reduce L₁ a L₂, y existe una MT M₂ que acepta L₂, entonces también existe una MT M₁ que acepta L₁: la que ejecuta primero M<sub>f</sub> sobre el input w y luego M₂ sobre el output f(w) de M<sub>f</sub>. Para este caso, en particular, la MT M₂ puede parar o no, y por lo tanto, también la MT M₁.  
    La prueba formal es la siguiente:
    * Supongamos que L₁ α L₂ y L₂ ∈ RE. Veamos si se cumple L₁ ∈ RE.
    * Por la hipótesis:
        * Existe una MT M<sub>f</sub> que computa una función que cumple w ∈ L₁ ↔ f(w) ∈ L₂.
        * Existe una MT M₂ que acepta L₂ y puede parar o no.
    * Así también, existe una MT M₁ que acepta L₁ y puede parar o no, por lo que:
        * Dado un input w.
        * M₁ ejecuta primero M<sub>f</sub> sobre w para obtener f(w).
        * Luego ejecuta M₂ sobre f(w).
        * Y acepta si y solo si M₂ acepta.
    * M₁ podría no parar porque M<sub>f</sub> y M₂ tampoco podrían necesariamente parar.
    * L₁=L(M₁) ya que w ∈ L₁ ↔ M<sub>f</sub>, a partir de w, computa f(w) ∈ L₂ ↔ M₂ acepta f(w) ↔ M₁ acepta w ↔ w ∈ L(M₁).

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