# Jerarquía de la Computabilidad. Problemas indecidibles

1. Recordar cómo probamos en la clase 2 que asumiendo R ⊂ RE se cumple RE ⊂ 𝓛 .

    La idea es encontrar un lenguaje L de RE - R. De esa manera, vale también que RE ⊂ 𝓛, porque deberá ser Lᶜ ∉ RE(si Lᶜ ∉ RE, como L ∈ RE, entonces L ∈ R), por lo que habremos encontrado un lenguaje Lᶜ de 𝓛 - RE.

2. Probar que los lenguajes Lᵤ = {(< M >,w) | M acepta w}, y HP = {(< M >,w) | M para sobre w} pertenecen a la clase RE. *Ayuda: las pruebas son similares a la desarrollada en la clase 3 para demostrar que D = {w<sub>i</sub>|M<sub>i</sub> acepta w<sub>i</sub>} ∈ RE.*

    //CORREGIR
    Veamos que Lᵤ = {(< M >,w) | M acepta w} ∈ RE
    
    La siguiente MT Mᵤ acepta el lenguaje Lᵤ. Dado un input (< M >, w), ejecuta M sobre w, y acepta si y sólo si M acepta a w.

    Veamos que HP = {(< M >,w) | M para sobre w} ∈ RE

    La sigueinte MT M<sub>HP</sub> acepta el lenguaje HP. Dado el input (< M >,w), M sobre w, y acepta si y solo si M para sobre w.

3. Explicar cómo enumeraría los números naturales pares, los números enteros, los números racionales y las cadenas de Ʃ* siendo Ʃ = {0, 1}.

4. En la clase 3 se probó que si HP ∈ R entonces R = RE, demostrando que si existe una M<sub>T</sub> M<sub>HP</sub> que decide HP, entonces para cualquier lenguaje L de la clase RE existe una MT M<sub>L</sub> que lo decide. En realidad, sólo se construyó M<sub>L</sub>. Se pide probar que efectivamente M<sub>L</sub> para siempre y que L(ML) = L.

5. De la misma manera que en el ejercicio anterior, se pide probar que efectivamente las MTM<sub>G</sub>y M<sub>F</sub> presentadas en la clase 3, deciden la Conjetura de Goldbach y el Ultimo Teorema de Fermat, respectivamente, si se asume que HP es recursivo. En otras palabras, se pide verificar la correctitud de la construcción de ambas MT.

6. Probar que la MT M<sub>20</sub> construida en la clase 3 para decidir el lenguaje L<sub>20</sub> = {< M > | M es una MT que a partir del input vacío λ nunca sale de las celdas 1 a 20}, efectivamente para siempre y acepta dicho lenguaje.

7. Probar que la MT M<sub>L</sub> construida en la clase 3 para aceptar L = {< M > | L(M) ≠ ø} efectivamente cumple que L(M<sub>L</sub>) = L.

8. Una función f: A ⟶ B se dice que es total computable, si y sólo si existe una MT M<sub>f</sub> que computa f para todo elemento a ∈ A. Sea la función f<sub>HP</sub> : Ʃ* ⟶{0, 1}, tal que:
    f(x) = 1,si x = (<M>, w) y M para a partir de w
    f(x) = 0,si x = (<M>, w) y M no para a partir de w, o bien x ≠ (< M >, w)
    Probar que la función f<sub>HP</sub> no es total computable.

Ayuda: Se podría probar que asumiendo que fHPes total computable,se llega a que HP es recursivo.En otras palabras, que se puede construir una MT que decide HP asumiendo que existe una MT que computa totalmente f<sub>HP</sub>.

9. Explicar(informal pero claramente) cómo sería una MT que genera la n-ésima fórmula booleana satisfactible, cuya sintaxis contiene variables de la forma x<sub>i</sub>, los operadores lógicos del conjunto {¬, ∧, ∨}, y paréntesis.

10. Responder cada uno de los incisos(justificar).
    1. Si L<sub>1</sub> ∈ RE y L<sub>2</sub> ∈ RE, ¿L<sub>1</sub> – L<sub>2</sub> ∈ RE?
    2. Si L<sub>1</sub> ⋂ L<sub>2</sub> ∈ RE, ¿L<sub>1</sub> o L<sub>2</sub> ∈ RE?
    3. Si L<sub>1</sub> ⋃ L<sub>2</sub> ∈ RE, ¿L<sub>1</sub> o L<sub>2</sub> ∈ RE?

11. Responder cada uno de los incisos(justificar).
    
    1. ¿Se puede decidir si una MT M, a partir de la cadena vacía λ, escribe alguna vez un símbolo no blanco? Ayuda: ¿Cuántos pasos puede hacer M antes de entrar en loop?
    2. ¿Se puede decidir si a partir de un input w, una MT M que sólo se mueve a la derecha para? Ayuda: ¿Cuántos pasos puede hacer M antes de entrar en loop?
    3. ¿Se puede decidir si dada una MT M existe un input w a partir del cual M para en a lo sumo 10 pasos? Ayuda: ¿Hasta qué tamaño de cadenas hay que chequear?
    4. ¿Se puede decidir si dada una MT M existe un input w de a lo sumo 10 símbolos a partir del cual M para? Ayuda: ¿En  este caso se puede acotar la ejecución de M considerando la cantidad de pasos, la cantidad de celdas recorridas u otro parámetro?