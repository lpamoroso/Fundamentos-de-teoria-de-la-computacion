# Práctica 2

1. Responder brevemente los siguientes incisos:

    1. ¿En qué difiere un lenguaje recursivo de un lenguaje recursivamente numerable no recursivo?

    Un lenguaje L es recursivamente enumerable(RE) si y solo si existe una MT M que lo acepte, es decir, L=L(M). En cambio, un lenguaje L es recursivo o decidible(R) si y solo si existe una MT M que lo acepta y siempre se detiene.

    2. ¿En qué difiere un lenguaje recursivamente numerable de uno que no lo es?

    Difiere en si para siempre o no. Si el lenguaje es recursivamente enumerable dado un w∉L, M<sub>L</sub> podría parar en q<sub>R</sub> o no parar. Si el lenguaje, en cambio, es recursivo, entonces para siempre: o bien en q<sub>A</sub>, o bien en q<sub>R</sub>.
    
    3. Probar que R⊆RE⊆*£*.

    Se cumple por definición. Se da que R⊆RE, ya que si un lenguaje posee una MT que con un lenguaje que acepta o rechaza(R), entonces esto entra en la definición de RE, ya que los lenguajes comprendidos allí poseen MT que los aceptan o bien rechazan o bien quedan loopeando. Habiendo probado que R⊆RE, resta probar que RE⊆*£*, lo cual, tambien se prueba del mismo modo, ya que se da que L es el conjunto de todos los lenguajes, sean reconocidos por una MT o no, por lo que RE representa una porción de los lenguajes: aquellos que una MT reconoce y acepta, para o simplemente loopea.

    4. ¿Cuándo un lenguaje está en la clase CO-RE? ¿Puede un lenguaje estar al mismo tiempo en la clase RE y en la clase CO-RE? ¿Para todo lenguaje de la clase CO-RE existe una MT que lo acepta?

    Cuando es un lenguaje complemento, con respecto a Ʃ*, de los lenguajes RE. Si, puede darse que un lenguaje esté en RE y CO-RE: en ese caso pertenece a R. No necesariamente existe una MT para todo lenguaje en CO-RE: dado que no todos son recursivos y hay algunos que son complemento, con respecto a Ʃ*, de los lenguajes de RE, hay muchos para los cuales no existirá una MT capaz de aceptarlos.
    
    5. Justificar por qué los lenguajes Ʃ* y ∅ son recursivos.

    Porque, para ámbos, puede construirse una MT que puede aceptar o rechazar.  
    La MT para justificar que Ʃ* es un lenguaje recursivo podría ser una que, sin importar input, siempre fuera a parar a q<sub>a</sub>. De esta manera, la m'aquina siempre aceptaría.
    Para ∅, la MT es mas simple: la idea sería una que, de ser el lenguaje input distinto a ∅, rechace.

    6. Si L⊆Ʃ* ¿Se cumple que L∈R?

    No necesariamente: para que pertenezca a R debe darse que exista una MT capaz de reconocerlo y que, además, o bien acepte, o bien se detenga.
    
    7. Justificar por qué un lenguaje finito es recursivo.

    Porque existe una MT capaz de reconocerlo y ésta, o bien lo acepta, o bien se detiene. Es decir, podría construirse una MT con dos cintas: una con el lenguaje input y otra con el lenguaje finito. La idea es ir comparando símbolo a símbolo y, si en algún momento no coincide, rechace; caso contrario, que acepte.
    
    8. Justificar por qué si L<sub>1</sub>∈CO-RE y L<sub>2</sub>∈CO-RE, entonces (L<sub>1</sub>⋂L<sub>2</sub>)∈CO-RE.

    Dado que CO-RE es cerrado en cuanto a intersección, entonces si L<sub>1</sub>⋂L<sub>2</sub> se da que (L<sub>1</sub>⋂L<sub>2</sub>)∈CO-RE. Esto se demuestra construyendo una MTU que en la que somete al input a la M<sub>1</sub> y luego, si acepta, a la M<sub>2</sub>. Si acepta, la MTU acepta; si rechaza en M<sub>1</sub> o en M<sub>2</sub>, la MTU rechaza.

2. Considerando el Lema 2 estudiado en la Clase Teórica 2(propiedad de clausura de la clase R con respecto a la operación de intersección):

    1. Indicar cómo se implementaría copiar el input w en la cinta 2 de la MT M construida.

    //No se como podría hacerse...

    2. Indicar cómo se implementaría borrar el contenido de la cinta 2 de M.

    Podría reemplazarse por B de derecha a izquierda hasta llegar a un B que indique que es el comienzo de la cinta.

    3. Probar la correctitud de la construcción:

        1. M para siempre.

        Se garantiza que M para siempre dado que 

        2. L(M) = L1⋂L2.

    4. Probar las otras propiedades de clausura de R mencionadas.

3. Considerando el Lema 3 estudiado en la Clase Teórica 2 (propiedad de clausura de la clase RE con respecto a la operación de unión):

    1. Indicar cómo se implementaría la suma de 1 al contador i en la MT M construida.
    2. Indicar cómo se implementaría ejecutar en M, i pasos de las MT M<sub>1</sub> y M<sub>2</sub>.
    3. Probar la correctitud de la construcción: L(M) = L<sub>1</sub>⋃L<sub>2</sub>.
    4. Probar las otras propiedades de clausura de RE mencionadas.

4. Considerando el Lema 4 estudiado en la Clase Teórica 2 (R = RE ⋂ CO-RE):
    1. Construir la MT M.
    2. Probar la correctitud de la construcción.