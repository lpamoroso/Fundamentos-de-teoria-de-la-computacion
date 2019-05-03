# Complejidad temporal

1. Responder y justificar brevemente las siguientes preguntas conceptuales:
    1. ¿Por qué sólo tiene sentido tratar la complejidad temporal dentro de la clase R?

        Porque es la única clase con lenguajes que resuelven problemas para los que sabemos que podemos construir una MT que puede aceptar o rechazar, necesariamente.
    
    2. Resolvimos de dos maneras el problema de los palíndromos, una con una MT de 1 cinta y otra con una MT con varias cintas. La primera tarda O(n²) pasos y la segunda O(n). Al igual que para otros problemas que manifiestan este comportamiento ¿Por qué es indistinta la cantidad de cintas utilizadas considerando la jerarquía temporal que definimos?

        Tanto n como n² lo resuelve en tiempo polinomial.

    3. Probar, utilizando la definición vista en clase, que n³ = O(2ⁿ).

        Porque, para cualquier valor n, la función n³ está siempre por debajo de 2ⁿ.

    4. Vimos que un algoritmo natural para encontrar un divisor que termine en 3 de un número N tarda O(n) pasos ¿Esto significa que el problema está en P?

        El problema de este problema(valga la redundancia) es que dividir es una operación que se prueba tarda tiempo poly(n), pero chequear que un número termina en 3 tarda tiempo O(n). El problema está claramente en NP y se aprecia que, a priori, no parece estar en P. De esto se puede concluir que construir aparentemente es más laborioso que verificar.

    5. Vimos que utilizando una MTN (MT no determinística),un algoritmo natural para encontrar un circuito de Hamilton en un grafo G tarda O(n²) pasos ¿Esto  significa que el problema está en P?

        No, ya que, si bien podemos construir una MT que compute en O(n²), lo cierto es que la cantidad de permutaciones es factorial y, por tanto, exponencial(solo puede obtenerse el camino fuerza bruta mediante), por lo que HC está en NP.

    6. El problema de los grafos isomorfos se representa por el lenguaje ISO = {(G1, G2) | G1 y G2 son grafos isomorfos}. Dos grafos son isomorfos si son idénticos salvo por el orden de sus vértices. Ej: el cuadrado con arcos (1,2), (2,3), (3,4) y (4,1) es isomorfo al cuadrado con arcos (1,2), (2,4), (4,3) y (3,1). Se prueba que ISO ∈ NP. Mostrar un certificado suscinto que caracterice al problema ISO.

        Una solución a este problema podría ser, usando una MTN, que en cada rama se realice una permutación distinta. La idea es, que en cada rama, se realice el chequeo si la disposición de vértices representa(o no) isomorfismo. Si alguna rama acepta, significa que existe una combinación tal que los grafos serían idénticos salvo por el orden de sus vértices. De esta forma, tenemos que una de las ramas podría ser (1,2), (2,3), (3,4) y (4,1); otra podría ser (1,2), (2,4), (4,3) y (3,1); y así siguiendo. Hay ramas que aceptarán y ramas que rechazarán. Con que una acepte es suficiente.

    7. Ligado al inciso anterior, considerando ahora el problema de los grafos no isomorfos, se pide mostrar un certificado asociado al problema ¿Es suscinto?

        Ante todo, no hay forma de dar un certificado suscinto de este problema porque es EXP, solo puedo dar certificado suscinto de problemas de NP. Si tuviera que dar un certificado, podría ser aquel en que, teniendo una MTN, rechazara en todas sus ramas, es decir, no hubiera ninguna combinación de vértices que hiciera que el grafo sea isomorfo. Sin embargo, para que sea suscinto, debería dar todas las combinaciones, y no puedo porque 

    8. Probar que la clase P es cerrada con respecto a la operación de complemento.

        Podría probar esto usando dos MT, M1 y M2, en la que M1 representa una MT que contiene a M2. M1 recibe un input w, el cual es computado por M2. Si M2 acepta, entonces M1 rechaza; y si M2 rechaza, M1 acepta. De esta manera queda probada la operación de complemento. 

2. Probar que si T₁(n) = O(T₂(n)), entonces TIME(T₁(n)) ⊆ TIME(T₂(n)).
_Ayuda: usar las definiciones estudiadas para probar la inclusión entre los conjuntos indicados._

    Para probar que esto se cumple, primero hay que plantear algunas definiciones:
    
    * Se define que una MT M trabaja en tiempo T(n) si y sólo si para toda entrada w, con |w| = n, M hace a lo sumo T(n) pasos.
    * Los problemas que pueden ser resueltos por MT que trabajan en tiempo O(T(n)) se agrupan en una misma clase: un problema (o lenguaje) pertenece a la clase TIME(T(n)) si y sólo si existe una MT, con una o más cintas, que lo resuelve o reconoce en tiempo O(T(n)).

    Partiendo de esas definiciones, yo tengo un tiempo T₁(n) que es igual al orden O(T₂(n)). Si ese T₁(n) es igual al orden O(T₂(n)), entonces ese O(T₁(n)), que va a representar al orden correspondiente de T₁(n), es igual al O(T₂(n)). Por definición, un problema o lenguaje pertenece a la clase TIME(T(n)) si y sólo si existe una MT, con una o más cintas, que lo resuelve o reconoce en tiempo O(T(n)). Tenemos un problema resuelto por una MT en O(T₁(n)). Entonces ese problema pertence a la clase TIME(T₁(n)). Del mismo modo, TIME(T₂(n)). Hay que evitar pasar por alto el detalle de que T₁(n) se puede representar con O(T₂(n)). Partiendo de eso, puedo incluir dentro de TIME(T₂(n)) a TIME(T₁(n)) ya que pude representar a T₁(n) con el orden que se usa para T₂(n).

3. Sea el lenguajeSMALL-SAT = {φ | φ es una fórmula booleana sin cuantificadores en  la  forma  normal  conjuntiva(o  FNC),  y  existe  una  asignación  de  valores  de  verdad  que  la satisface  en  la  que  hay  a  lo  sumo 3variables  con  valor  de  verdad  verdadero}. Probar  que SMALL-SAT ∈P.
_Comentario: φ está en laFNC  si  es  una  conjunción  de  disyunciones  de variables o variables negadas, como p.ej. (x1x2) x4(x3 x5 x6)._
4. El  problema  del conjunto  dominante de un  grafo  se  representa  por  el  lenguaje DOM-SET  =  {(G,  K)  | G  es  un grafo que  tiene  un  conjunto  dominante  de  K  vértices}.  Un subconjunto de vértices de un grafo G es un conjunto dominante de G, si todootro vértice de G es adyacente a  algún vértice de dicho subconjunto.  Probar que DOM-SET ∈NP. ¿Se cumple que DOM-SET ∈P? ¿Se cumple que DOM-SETC ∈NP? Justificar las respuestas.
5. Asumamos que Ʃ* sólotiene cadenas de unos y ceros, pudiendo incluir la cadena vacía λ. En este contexto, dada una cadena w de Ʃ*, se define como E(w) a su cadena espejo, que  es  la  que  se  obtienereemplazando  en  w  los  unos  por  ceros  y  los  ceros  por  unos  (p.ej. E(1001) = 0110y E(λ) = λ), y también se define que L es un lenguaje espejo si se cumple,para toda cadena wdistinta de λ,que w ∈L E(w) ∈LC. Sea f la función que transforma todo w en E(w). Responder, justificando las respuestas:
    1. ¿Es f una función total computable?
    2. ¿Cuánto tarda una MT que computa f?
    3. Si L es un lenguaje espejo, ¿se cumple que f es una reducción polinomial de L a LC?
6. Hemos  construido  en  la  Clase  6 una  reducción  polinomial  del  problema  CH (circuito de Hamilton) al problema TSP (viajante de comercio), es decir CH αPTSP.
    1. Sabiendo que TSP es NP-completo y sin asumir nada sobre CH:
        1. ¿Se cumple que CH ∈NP?
        2. ¿Se cumple que CH ∈NPC?
    2. Sabiendo que CH es NP-completo y sin asumir nada sobre TSP:
        1. ¿Se cumple que TSP ∈NP?
        2. ¿Se cumple que TSP ∈NPC?
7. En la Clase 6 quedó planteado como ejercicio probar que si L1αPL2, L1∈NPC y L2∈NP, entonces L2∈NPC.Probarlo.
8. En la Clase 6 quedó planteado como ejercicio probar que si L1∈NPC y L2∈NPC, entonces se cumple tanto L1αPL2comoL2αPL1.Probarlo.

cert suscinto: dos condiciones se veridiica en tiempo polinomial y ocupa espacio polinomial
hacer un mapa de los problemas tanto en computabilidad como complejidad.