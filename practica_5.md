# Complejidad temporal

1. Responder y justificar brevemente las siguientes preguntas conceptuales:
    1. ¿Por qué sólo tiene sentido tratar la complejidad temporal dentro de la clase R?

        Porque es la única clase con lenguajes que resuelven problemas para los que sabemos que podemos construir una MT que puede aceptar o rechazar, necesariamente.
    
    2. Resolvimos de dos maneras el problema de los palíndromos, una con una MT de 1 cinta y otra con una MT con varias cintas. La primera tarda O(n2) pasos y la segunda O(n).Al igual que  para  otros  problemas  que  manifiestan  este  comportamiento,  ¿por  qué  es  indistinta  la cantidad de cintas utilizadas, considerando la jerarquía temporal que definimos?
    3. Probar, utilizando la definición vista en clase, que n3= O(2n).
    4. Vimos que un algoritmo natural para encontrar un divisor que termine en 3 de un número N tarda O(N) pasos. ¿Esto significa que el problema está en P?
    5. Vimos que utilizando una MTN (MT no determinística),un algoritmo natural para encontrar un  circuito  de  Hamilton  en  un  grafo  G  tarda O(n2)  pasos.  ¿Esto  significa  que  el  problema está en P?
    6. El problema de los grafos isomorfos se representa por el lenguaje ISO = {(G1, G2) | G1y G2son grafos isomorfos}. Dos grafos son isomorfos si son idénticos salvo por el orden de sus vértices. P.ej.el cuadrado con arcos (1,2), (2,3), (3,4) y (4,1) es isomorfo al cuadrado conarcos  (1,2),  (2,4),  (4,3)  y  (3,1).  Se  prueba  que  ISO ∈NP. Mostrar  un certificado suscinto que caracterice al problema ISO.
    7. Ligado  al  inciso  anterior,  considerando  ahora  el  problema  de  los  grafos  no  isomorfos,se pide mostrar un certificado asociadoal problema. ¿Es suscinto?
    8. Probar que la clase P es cerrada con respecto a la operación de complemento.
2. Probar  que  si  T1(n)  =  O(T2(n)),  entonces TIME(T1(n)) TIME(T2(n)).Ayuda:  usar las definiciones estudiadas para probar la inclusión entre los conjuntos indicados.
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