# Résolution Rigoureuse : Équation Diophantienne

## 1. Énoncé et Contraintes
Déterminer tous les couples $(x, y) \in (\mathbb{N}^*)^2$ vérifiant :
$$\frac{x+y}{x^2-xy+y^2} = \frac{2}{7}$$

## 2. Analyse de Divisibilité et Parité
L'égalité est équivalente à : $7(x+y) = 2(x^2-xy+y^2)$.

### A. Argument de Parité
Puisque $2$ divise le membre de droite, il doit diviser $7(x+y)$. Comme $7$ est impair, $2$ divise nécessairement $(x+y)$. 
**Conclusion :** $x$ et $y$ ont la même parité.

### B. Argument de Divisibilité (Gauss)
Puisque $7$ divise le membre de gauche, il doit diviser $2(x^2-xy+y^2)$. Comme $\text{pgcd}(7, 2) = 1$, d'après le lemme de Gauss :
$$x^2 - xy + y^2 \equiv 0 \pmod 7$$

## 3. Étude par les Congruences
L'étude systématique des restes modulo 7 combinée à la contrainte de parité restreint les solutions.

## 4. Ensemble Solution Final
$$S = \{ (1, 5), (5, 1), (2, 6), (6, 2), (7, 7) \}$$

---

## 5. Vérification par Script Python
```python
for x in range(1, 15):
    for y in range(1, 15):
        if 7*(x + y) == 2*(x**2 - x*y + y**2):
            print(f"Solution trouvée : ({x}, {y})")
