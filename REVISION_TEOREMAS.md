# Revisión de teoremas, lemas y demostraciones

Alcance: `tex/cap1.tex`, `tex/cap2.tex` y `tex/cap3.tex`. El capítulo 4 no contiene teoremas.
Los resultados citados de libros o artículos (Han, Brezis, Lozinski, Duprez, Di Pietro) no se pudieron
consultar. Se revisó que el enunciado sea correcto y que la cita sea coherente con él, pero no la
demostración original. Las comprobaciones algebraicas se hicieron a mano.

Leyenda: **E** = error (el enunciado o la demostración son falsos o no válidos tal como están);
**G** = hueco (el resultado probablemente es cierto, pero faltan pasos o hipótesis);
**T** = errata de escritura; **OK** = verificado.

## 1. Resultados propios de la tesis (cap. 3)

| Resultado | Estado | Observación |
|---|---|---|
| Def. de $\mathcal{F}_h^\Gamma$ | **E** | Dice $e\cap\partial\Omega_h^\Gamma=\emptyset$. Con eso se excluyen las aristas $F_k$ entre $T_k$ y los elementos de la banda, que están en $\partial\Omega_h^\Gamma$. Debe ser $e\cap\partial\Omega_h=\emptyset$ (aristas interiores de $\mathcal{T}_h$). Sin $F_k$, el Lema 4 (α) es falso, porque necesita el salto nulo en $F_k$. |
| Lema $\alpha$ | **E/G** | (a) Se usa $\lvert\Delta v\rvert^2\le\lvert\Delta v-\beta v\rvert^2+\lvert\beta v\rvert^2$. Es falso; lo correcto es factor 2 (basta cambiar $\lambda$ por $\lambda/2$). (b) En la demostración $\lambda$ se sustituye por $\beta$ en varias líneas. (c) $\alpha=\max_{\Pi_k,v}F$ se toma sobre infinitas configuraciones geométricas $\Pi_k$, así que hace falta un argumento de escala y compacidad (mallas regulares, a lo más $M$ elementos). No hay uno. (d) El máximo debe tomarse sobre $v$ no constante, no sobre $v\neq0$. (e) La Premisa 3 no asegura que $\Pi_k$ sea conexo por aristas, y la demostración propaga "$v=c$" de elemento en elemento. Debe exigirse esa conexión. (f) $\lvert v\rvert_{1,\Pi_k^\Gamma}\le\lvert v\rvert_{1,\Pi_k}^2$ debería tener cuadrados en ambos lados. |
| Proposición (coercividad) | **G** | Resultado plausible (Duprez–Lozinski), pero faltan pasos. (1) Pasa de $-\varepsilon C h^{-2}\lVert v\rVert^2_{0,\Omega_h^\Gamma}$ a $-\varepsilon C^3 h^{-2}\lVert v-\tfrac1h\phi q\rVert^2$ sin justificarlo. Falta usar el Lema `trazaraiz`, que además genera un término $\varepsilon C^2\lvert v\rvert^2_1$. (2) El término $-\lambda\beta^2h^2\lVert v\rVert^2$ del Lema α desaparece sin explicación. Absorberlo con $h\le h_0=\operatorname{diam}\Omega$ da una constante $\lambda\beta^2h_0^4$ que compite con $\varepsilon$. Además $\alpha$ depende de $\lambda$. Hay que ordenar la elección $\lambda\to\alpha\to\varepsilon\to\gamma,\sigma$. (3) El enunciado usa $\lVert\Delta v\rVert$ y la demostración $\lVert\Delta v-\beta v\rVert$. Para $\beta=1$ (nutrientes) no son equivalentes sin trabajo extra. (4) La $M$ final mezcla $\sigma$ y $\sigma_D$, y resta $\beta$ de $\sigma_D$ sin que esa resta aparezca en las líneas anteriores. (5) La línea con $-\lVert v_h\rVert^2_{0,\Gamma_h}\ge-\tfrac{C^2}{h}\lVert\cdot\rVert$ no tiene el cuadrado y no se usa después. |
| Teorema de existencia y unicidad | **G/T** | (1) No enuncia las hipótesis que usa: $\gamma,\sigma$ grandes, Premisas 1–3, $h\le h_0$. (2) $\vert\!\vert\!\vert\cdot\vert\!\vert\!\vert$ está definida sin raíz cuadrada, así que no es una norma. (3) Escribe "$v=\tfrac1h\phi_h$" y le falta $q$. (4) Las ecuaciones (`problemach`, `problemaph`) tienen $w_h$ en la posición de la función test; debe ser $q_h$. El argumento de fondo (coercividad $\Rightarrow$ solución trivial del problema homogéneo $\Rightarrow$ unicidad $\Rightarrow$ existencia, en dimensión finita) es correcto. |
| Lema `triangulo` (cita Duprez–Lozinski) | **OK** | Un polinomio armónico con $p=\partial_np=0$ en un segmento es nulo (analiticidad). Está citado, no demostrado. |
| Lemas `trazaraiz`, `traza`, `trazaq` | **OK** (citados) | Enunciados estándar. Dependen de que la banda tenga ancho $\sim h$ (Premisas 1–2). |
| Proposición de extensión de velocidad (unicidad discreta) | **OK** | La forma es simétrica semidefinida positiva. Con $\epsilon>0$ el cálculo $(x,y)(A+\epsilon I)(x,y)^T=(x\phi_x+y\phi_y)^2+\epsilon\lvert(x,y)\rvert^2$ es correcto. Se concluye $S=c$, $c=0$ en $\Gamma_h$ ($\phi_h=0$) y luego $p=0$. Aviso menor: $p_h$ se usa como la presión y como multiplicador. |
| Teorema de interpolación (p. 412 de Han) | **OK/T** | El enunciado es correcto. La hipótesis "$\mathbf{P}_k(T)\subset\mathbf{X}_h$" está mal escrita: debería ser $\mathbf{X}_h\vert_T=\mathbf{P}_k(T)$. |
| Proposición de curvatura (Shopple) | **OK/G** | La consistencia $O(h^2)$ es cierta (momento de primer orden nulo por simetría del parche). La cota $\lvert\kappa_0\rvert\le3\sqrt2/h$ también lo es. El valor exacto en la malla uniforme con diagonales es $(2+\sqrt2)/h\approx3.41/h$. Faltan las hipótesis $\phi\in C^3$ y $\nabla\phi\ne0$ en $D$. |
| Derivación de características Galerkin | **T** | Usa $o(\Delta t^2)$; el resto es $O(\Delta t^2)$ (aparece el término $\tfrac12\Delta t^2S^{T}\nabla^2\phi\,S$). La conclusión (esquema de primer orden) es correcta. |

## 2. Cap. 2 (no son teoremas, pero afectan al modelo)

| Punto | Estado | Observación |
|---|---|---|
| Definición de $P$ | **E** | Se define $P=\bar p+(1-U)G-AG\frac{\lvert x\rvert^2}{4}$. Con $\Delta\bar p=-GU+AG$ y $\Delta U=U$ eso da $\Delta P=-2GU\ne0$. Para que $P$ sea armónica debe ser $P=\bar p-(1-U)G-AG\frac{\lvert x\rvert^2}{4}$. Esta definición es coherente con la fórmula de $V_n$ ($+G\nabla U\cdot n$) y con el código, así que es una errata en la definición. |
| Curvatura con $\phi$ | **E** | El denominador debe ser $(\phi_x^2+\phi_y^2)^{3/2}$, no $^{1/2}$. Solo coincide si $\lvert\nabla\phi\rvert=1$. |
| $\partial_t\lvert\nabla\phi\rvert^2$ | **T** | Falta el factor $\tfrac12$: de la derivación sale $\tfrac12\partial_t\lvert\nabla\phi\rvert^2+\tfrac12S\cdot\nabla\lvert\nabla\phi\rvert^2=0$. La conclusión (la propiedad de distancia se conserva a lo largo de $S$) se mantiene, pero conviene decir que es transporte a lo largo de las características. |
| Solución circular: $P(R)$ | **E** | Dice $\frac1R-AG\frac R4$. Es $\frac1R-AG\frac{R^2}{4}$. No afecta a $V$, porque $P$ es constante. |
| Solución circular: $V=GR(1/w_0-A/2)$ | **OK** | $w_0=xI_0/I_1$ estrictamente creciente con $w_0(0^+)=2$ y $x<w_0<\sqrt{x^2+1}+1$. Se verificó que $w_0=2/A$ tiene solución única solo si $A<1$, y las cotas de $R_\infty$ son correctas. |
| Solución circular: casos $G\ge0$ | **G** | Con $G=0$ se tiene $V\equiv0$, no hay $R_\infty$ único. Los casos "$V<0$" y "$V>0$" requieren $G>0$. |
| Solución circular: caso $G<0$, $A>0$ | **E** | Se dice que el tumor "alcanza un punto de equilibrio". Con $G<0$ y $0<A<1$, $V<0$ si $R<R_\infty$ y $V>0$ si $R>R_\infty$, así que $R_\infty$ es un equilibrio **inestable**. Para $A\ge1$ el crecimiento es siempre positivo. Además "acelerado" no se prueba, solo $V>0$. |

## 3. Cap. 1 (teoremas citados)

| Resultado | Estado | Observación |
|---|---|---|
| Densidad de $C_c^\infty$ en $L^p$; Meyers–Serrin; densidad en dominios Lipschitz; $W^{k,p}$ Banach; Poincaré en $W_0^{1,p}$; segunda fórmula de Green | **OK** | Enunciados correctos. |
| Fórmula de Green (1.ª) | **T** | En el primer miembro derecho aparece $\mathbf{d}\Gamma$ donde debe ir $\mathbf{d}x$. |
| Sobolev (embeddings) | **T** | El caso $1/p-k/d<0$ escribe $C^{\cdot,\beta}(\Omega)$; debe ser $C^{\cdot,\beta}(\overline\Omega)$. |
| Trazas (parte $m>1+1/p$, dominio $C^{1,1}$) | **G** | Para $m$ grande la frontera debe ser al menos $C^{\lceil m\rceil-1,1}$. Con $C^{1,1}$ fijo el enunciado solo vale para $m\le2$. Hay que verificarlo contra la fuente. |

## 4. Resumen

- Los resultados propios de la tesis (coercividad y existencia/unicidad del método φ-FEM) son plausibles y
  siguen la línea de Duprez–Lozinski. Tal como están escritos **no están bien demostrados**:
  - hay un error de definición (`F_h^Γ`) que invalida el Lema α;
  - hay una desigualdad falsa en el Lema α;
  - hay pasos omitidos en la coercividad;
  - hay hipótesis faltantes en el teorema.
- Cap. 2 tiene tres errores que conviene corregir antes de la defensa: el signo en $P$, el exponente de la curvatura y el caso $G<0$.
- Los teoremas del cap. 1 son estándar. Quedan solo erratas y una condición de regularidad por verificar.
