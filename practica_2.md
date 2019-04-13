# Jerarquía de la Computabilidad

1. Responder brevemente los siguientes incisos:

    1. ¿En qué difiere un lenguaje recursivo de un lenguaje recursivamente numerable no recursivo?

    Un lenguaje L es recursivamente enumerable(RE) si y solo si existe una MT M que lo acepte, es decir, L=L(M). En cambio, un lenguaje L es recursivo o decidible(R) si y solo si existe una MT M que lo acepta y siempre se detiene.

    2. ¿En qué difiere un lenguaje recursivamente numerable de uno que no lo es?

    Difiere en si para siempre o no. Si el lenguaje es recursivamente enumerable dado un w∉L, M<sub>L</sub> podría parar en q<sub>R</sub> o no parar. Si el lenguaje, en cambio, es recursivo, entonces para siempre: o bien en q<sub>A</sub>, o bien en q<sub>R</sub>.
    
    3. Probar que R⊆RE⊆𝓛 .

    Se cumple por definición. Se da que R⊆RE, ya que si un lenguaje posee una MT que con un lenguaje que acepta o rechaza(R), entonces esto entra en la definición de RE, ya que los lenguajes comprendidos allí poseen MT que los aceptan o bien rechazan o bien quedan loopeando. Habiendo probado que R⊆RE, resta probar que RE⊆𝓛 , lo cual, tambien se prueba del mismo modo, ya que se da que L es el conjunto de todos los lenguajes, sean reconocidos por una MT o no, por lo que RE representa una porción de los lenguajes: aquellos que una MT reconoce y acepta, para o simplemente loopea.

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

2. Considerando el Lema 2 estudiado en la Clase Teórica 2(propiedad de clausura de la clase R con respecto a la operación de intersección): //REVISAR

    1. Indicar cómo se implementaría copiar el input w en la cinta 2 de la MT M construida.

    La idea sería, en cada estado, ir copiando un caracter de una cinta a la otra a través de las transiciones.

    2. Indicar cómo se implementaría borrar el contenido de la cinta 2 de M.

    De la misma manera que se copia, se borra; la diferencia es que en cada caracter borrado se pone un B para indicar que está en blanco.

    3. Probar la correctitud de la construcción:

        1. M para siempre.

        Se garantiza que M para siempre dado que es una de las propiedades garantizadas por R. La idea general es que un input cualquiera pase por entre dos MT que, o bien aceptan, o bien rechazan. Sea cual fuere el caso, la MT necesariamente aceptará o rechazará.

        2. L(M) = L<sub>1</sub> ⋂ L<sub>2</sub>.

        Partiendo también de la idea general, se garantiza que el lenguaje L es la intersección de L<sub>1</sub> y L<sub>2</sub> dado que primero pasará por una MT que reconozca L<sub>1</sub>. Solo si acepta, pasará por la MT de L<sub>2</sub>. Si, en cual instancia, rechazare, el input no aceptare.

    4. Probar las otras propiedades de clausura de R mencionadas.

    Restan probar las propiedades de complemento, unión y concatenación.

    **Unión**: la idea sería pasar el input w por dos MT, una que reconozca L<sub>1</sub> y, si al menos uno de los símbolos está en L<sub>1</sub>, que pase a la MT que reconoce L<sub>2</sub>. En el caso de ésta última MT, se debe reconocer que los símbolos que no estaban en L<sub>1</sub> estén allí. Debe llevarse registro de si el símbolo fue encontrado en algún lenguaje, para luego al final proceder a tomar la decisión.
    **Complemento**: la idea es construir una MT que, para cualquier input w, si éste acepta, entonces que rechace y, si rechaza, que entonces acepte.
    **Concatenación**: la idea sería construir una MT que reconozca alguna cadena de L<sub>1</sub> en el input w. Si existe alguna cadena que encaja al principio, se sobreescribe esa parte con B en L para marcar que fue procesada y se deriva a la MT que reconoce L<sub>2</sub>. Se realiza lo mismo que antes, con la diferencia que si hay alguna caden a que coincida acepta definitivamente. Si no llegara a aceptar en alguna instancia, la MT rechaza.

3. Considerando el Lema 3 estudiado en la Clase Teórica 2 (propiedad de clausura de la clase RE con respecto a la operación de unión): //REVISAR

    1. Indicar cómo se implementaría la suma de 1 al contador i en la MT M construida.

    A priori, la MT no sabe contar en el sentido de establecer un número y que la MT sepa como llegar sin mucho problema. Lo que yo haría es que, dada una cantidad de pasos finita, se construyen tantos estados como pasos. La idea es ir pasando de estado en estado y dar la ilusión de que la máquina incrementa, sin embargo, de la manera que acá se plantea siempre será una cantidad finita y deberá programarselo por detrás.

    2. Indicar cómo se implementaría ejecutar en M, i pasos de las MT M<sub>1</sub> y M<sub>2</sub>.

    Esto es más de lo discutido arriba: se ejecuta M y, por cada paso, se cambia a otro estado hasta que, eventualmente, no hayan más estados para cambiar. La ejecución de M se da haciendo que M<sub>1</sub> reconozca L<sub>1</sub> y M<sub>2</sub>, L<sub>2</sub>.//PREGUNTAR CUÁNDO ACEPTA, SI ACEPTA CUANDO ACEPTA UNA O NECESARIAMENTE LAS DOS.

    3. Probar la correctitud de la construcción: L(M) = L<sub>1</sub> ⋃ L<sub>2</sub>.

    //ANTES PREGUNTAR LO ANTERIOR.

    4. Probar las otras propiedades de clausura de RE mencionadas.

    Resta probar la intersección y la concatenación.

    **Concatenación**: en este caso, es parecido a la concatenación en R, solo que esta vez se hace en paralelo para evitar los problemas de RE. Para esto se requieren tres cintas(una para contar las pasadas, otra para medir el input de la primera parte de L y otra cinta para medir el input de la última parte de L). Luego se simulan las pasadas sobre la quinta y sexta cinta. Si aceptan, la cosa queda ahí. Si no, se chequea que no se haya llegado al límite de pasos y, de no haberse llegado se procede a seguir intentando.
    **Intersección**: //PREGUNTAR

4. Considerando el Lema 4 estudiado en la Clase Teórica 2 (R = RE ⋂ CO-RE):
    1. Construir la MT M.

    La idea general del asunto son dos MT: por un lado M y, por otro, Mᶜ que reconocen a L y Lᶜ, respectivamente. Si M se detiene en qₐ, entonces la MT acepta; si Mᶜ se detiene en qₐ, la MT rechaza.

    2. Probar la correctitud de la construcción.

    Se garantiza la correctitud dado que siempre w ∈ L o w ∈ Lᶜ, por lo que la MT acepta o rechaza siempre.

5. Verificar la correctitud de las construcciones de las MT efectuadas en la Clase Práctica 2, es decir las correspondientes a las pruebas de: 

    1. La propiedad de clausura de R con respecto a la operación de concatenación.

    //DEPENDE DE LA RESPUESTA DEL PUNTO ANTERIOR

    2. La propiedad de clausura de RE con respecto a la operación de concatenación.
    
    //DEPENDE DE LA RESPUESTA DEL PUNTO ANTERIOR

    3. La propiedad de clausura de RE con respecto a la operación de unión utilizando una MTN.
    
    //DEPENDE DE LA RESPUESTA DEL PUNTO ANTERIOR

6. Sean L<sub>1</sub> y L<sub>2</sub> dos lenguajes recursivamente numerables de números naturales representados en notación unaria(por ejemplo, el número 5 se representa con 11111). Probar que también es recursivamente numerable el lenguaje L = {x | x es un número natural representado en notación unaria, y existen y, z, tales que *y + z = x*, con *y ∈ L<sub>1</sub>*, *z ∈ L<sub>2</sub>*}. *Ayuda: la prueba es similar a la de la propiedad de clausura de la clase RE con respecto a la operación de concatenación.*

7. Dada una MT M<sub>1</sub> con Ʃ = {0, 1}:
    1. Construir una MT M<sub>2</sub>que determine si L(M<sub>1</sub>) tiene al menos una cadena.
    2. ¿Se puede construir además una MT M<sub>3</sub> para determinar si L(M<sub>1</sub>) tiene a lo sumo una cadena Justificar.
    
Ayuda para la parte (1): Si L(M<sub>1</sub>)tiene al menos una cadena, entonces existe al menos una cadena w de unos y ceros, de tamaño n, tal que M<sub>1</sub> a partir de w acepta en k pasos. Teniendo en cuenta esto, pensar cómo M<sub>2</sub> podría simular M<sub>1</sub> considerando todas las cadenas de unos y ceros hasta encontrar eventualmente una que M<sub>1</sub> acepte(¡Cuidándose de los casos en que M<sub>1</sub> entre en loop!).