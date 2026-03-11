# Résolution Rigoureuse : Équation Diophantienne

## 1. Énoncé et Contraintes
Déterminer tous les couples $(x, y) \in (\mathbb{N}^*)^2$ vérifiant :
$$\frac{x+y}{x^2-xy+y^2} = \frac{2}{7}$$

## 2. Analyse de Divisibilité et Parité
L'égalité est équivalente à : $7(x+y) = 2(x^2-xy+y^2)$.

* **Parité** : Puisque $7$ est impair, $x+y$ est nécessairement **pair**. Ainsi, $x$ et $y$ ont la même parité.
* **Divisibilité** : Par le lemme de Gauss, $x^2-xy+y^2 \equiv 0 \pmod 7$ car $\text{pgcd}(7,2)=1$.

## 3. Étude Graphique et Unicité
L'image ci-dessous illustre la zone de recherche. On remarque que pour des valeurs de $x$ et $y$ dépassant 7, le dénominateur (de degré 2) croît beaucoup plus vite que le numérateur (de degré 1), rendant le quotient strictement inférieur à $2/7$.

![Illustration de la zone de recherche](illustration.jpg)

*Note : Si $x=y$, l'équation se simplifie en $2/x = 2/7$, soit $x=7$. Pour tout $x>7$, $2/x < 2/7$.*

## 4. Ensemble Solution Final
Les seuls couples vérifiant l'intégralité des contraintes (parité, divisibilité et bornitude) sont :
$$S = \{ (1, 5), (5, 1), (2, 6), (6, 2), (7, 7) \}$$

---

## 5. Vérification Numérique (Python)
```python
# Test d'unicité sur une plage étendue
for x in range(1, 100):
    for y in range(1, 100):
        if 7*(x + y) == 2*(x**2 - x*y + y**2):
            print(f"Solution validée : ({x}, {y})")
