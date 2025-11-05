## Pesquisa — Passo variável em Gradient Descent (GD)

### Backtracking (Armijo)
Escolhe o valor de \( \alpha \) por tentativas decrescentes  
\[
\alpha, \; \beta \alpha, \; \beta^2 \alpha, \dots
\]
até satisfazer:
\[
f(x - \alpha \nabla f) \le f(x) - c\,\alpha \|\nabla f\|^2
\]
É robusto e garante decréscimo monotônico da função objetivo.

---

### Wolfe / Strong Wolfe
Versão aprimorada do Armijo com uma condição de curvatura adicional.  
É usada em métodos como BFGS e Conjugate Gradient.

---

### Busca Exata (Line Search)
Para funções quadráticas:
\[
f(x) = \frac{1}{2}x^\top Hx + b^\top x + c
\]
O passo ótimo é:
\[
\alpha^* = \frac{g^\top g}{g^\top H g}
\]
Esse método encontra o melhor passo em uma única direção.

---

### Barzilai–Borwein
Estima \(\alpha\) usando informações das duas últimas iterações:
\[
\alpha_k = \frac{s_{k-1}^\top s_{k-1}}{s_{k-1}^\top y_{k-1}}
\]
onde \( s_{k-1} = x_k - x_{k-1} \) e \( y_{k-1} = \nabla f_k - \nabla f_{k-1} \).  
Converge rapidamente na prática.

---

### Passo decrescente
Define \(\alpha_k\) decrescendo com as iterações, por exemplo:
\[
\alpha_k = \frac{1}{k}
\]
É simples, porém lento.

---

### Aplicação
Para \( f(x,y) = 3x^2 + 3xy + 2y^2 + x - y \),  
com Hessiana \( H = \begin{bmatrix} 6 & 3 \\ 3 & 4 \end{bmatrix} \),  
a **busca exata** é o método mais natural e eficiente.
