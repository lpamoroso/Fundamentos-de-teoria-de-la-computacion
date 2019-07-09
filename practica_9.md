# Parte 2: Lógica e inteligencia artificial.

## Práctica 4:

1. Expresar en un lenguaje de predicados de primer orden las siguientes afirmaciones:

    1. “Algunas aves no vuelan”
    2. “No todas las aves vuelan”

    Analizar la relación entre ambas. Mostrar cómo se puede transformar una expresión en la otra.

2. Escribir las siguientes proposiciones usando un lenguaje de predicados de primer orden:
    1. El cero es el menor natural.
    2. El conjunto vacío está incluido en cualquier conjunto.
    3. Si se prueba una propiedad para el cero y luego se prueba que esa misma propiedad vale para el número n+1 si vale para n, entonces se ha probado que la propiedad vale para cualquier natural.
    4. Si hay un número natural que cumple una cierta propiedad, entonces hay un mínimo natural que cumple esa propiedad.

3. Expresar en un lenguaje de predicados de primer orden el conocimiento asociado a las siguientes situaciones:
    1. Ningún dragón que viva en un zoológico es feliz. Cualquier animal que encuentre gente amable es feliz. Las personas que visitan los zoológicos son amables. Los animales que viven en zoológicos encuentran personas que visitan zoológicos.

    Encontrar suposiciones adicionales que permitan concluir que ningún dragón vive en un zoológico.

    2. Todo peluquero afeita a todo aquél que no se afeita a sí mismo. Ningún peluquero afeita a alguien que se afeite a sí mismo.

    Con el conocimiento disponible ¿Se puede deducir que los peluqueros no existen?

    3. Si alguien hace algo bueno, ese alguien es bueno. Del mismo modo, si alguien hace algo malo, es malo. Sebastián ayuda a su madre y también miente algunas veces. Mentir es malo y ayudar es bueno. 

    Determinar si con el conocimiento disponible es posible deducir que Sebastián es bueno ¿Y es posible deducir que es malo?

4. Dar interpretaciones para los siguientes lenguajes de primer orden, y traducir en cada caso las fórmulas presentadas a oraciones apropiadas en lenguaje natural.
    1. ∀(x)∀(y)(A<sub>1</sub><sup>2</sup>(x, y) →  A<sub>1</sub><sup>2</sup>(y, x))
    2. ∀(x) A1 2(x, x)
    3. ∀(x)∀(y)∀(z)(A<sub>1</sub><sup>2</sup>(x, y) ⋀ A<sub>1</sub><sup>2</sup>(y, z) → A<sub>1</sub><sup>2</sup>(x, z))
    4. ∀(x)(A<sub>1</sub><sup>2</sup>(x, c) → A<sub>1</sub><sup>2</sup>(x, f(y)))
    5. ∀(x) ⌐ A<sub>1</sub><sup>2</sup>(x, x)
    6. ∀(x)∀(y) A<sub>1</sub><sup>2</sup>(x, y)