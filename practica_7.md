# Parte 2: Lógica e inteligencia artificial.

## Práctica 2:

1. Retome el Ejercicio 1 de la Práctica 1:

    1. Seleccione un par de enunciados que sean lógicamente equivalentes(que tengan el mismo significado). Demuéstrelo mediante tablas de verdad.

        Enunciados 2 y 4. Ambos siguen la estructura (p → q). Su tabla de verdad es la siguiente:

        (p | → | q)
        :---:|:---:|:---:
        V | V | V
        F | V | V
        V | F | F
        F | V | F

    2. Para el ítem ii, construya dos enunciados que sean lógicamente equivalentes.

        Dos ejemplos son (⌐p ⋁ q) y (⌐q → ⌐p).

    3. Para el ítem vii, construya dos enunciados que sean lógicamente equivalentes.

        Siguiendo la lógica de arriba, dos ejemplos son (⌐((p ⋀ q ⋀ r) ⋁ (q ⋀ s)) ⋁ t) y (⌐t → ⌐((p ⋀ q ⋀ r) ⋁ (q ⋀ s))).

2. Fundamentar:

    1. Si v(A ⋀ B) = F y v(A ⋁ B) = V entonces v(A) = v(⌐B)?
    2. Si v(A → B) = F y v(A ⋁ B) = V entonces v(A) = v(⌐B)?

    Nota: v es una función de valuación.

3. Para las tablas dadas a continuación, encontrar alguna fbf de la Lógica de Enunciados que las tenga por tablas de verdad.

    _Ayuda: alcanza con usar p, q, ⋁, ⋀, ⌐_

    ![tablas_verdad](img/tablas_verdad.png)

    La primera tabla representa (p ⋁ q); la segunda, ⌐(p ⋁ q); la tercera, ⌐(p ⋁ q) ⋁ (p ⋁ q); y la cuarta, ⌐(p ⋀ q) ⋁ ⌐(p ⋀ q).

4. Sean A, B, C y D formas enunciativas. Se sabe que A → B es una contradicción y que C → D es una tautología. Determinar, si es posible, cuáles de las siguientes formas enunciativas son tautologías y cuáles contradicciones. Justificar las respuestas.

    1. (C → B) ⋁ (D → B)
    2. (A → C ) ⋁ (B → D)
    3. (A → D) ⋀ (B → D)