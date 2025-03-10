# Variables aleatorias discretas

## Variables aleatorias discretas

**VARIABLE ALEATORIA**

Una variable aleatoria $X$ es una fucnión sobre el espacio muestral, que a cada posible suceso $A \subset E$ le corresponde un valor real. Es decir:
$$X : E \to \mathbb{R}, \quad A \mapsto X(A)$$

**VARIABLE ALEATORIA DISCRETA**

Cuando la variable toma un número contable (finito o infinito numerable) de valores, decimos que es una **variable aleatoria discreta**:
$$X : E \to \mathbb{N}$$

<ins>Ejemplo</ins>:

Sea el experimento consiste en lanzar una monedas tres veces seguidas y
observar el número de caras ($\mathcal{C}$) y cruces ($\mathcal{R}$) que se obtienen. El espacio muestral asociado a dicho experimento aleatorio es:

$$E = \{\mathcal{CCC}, \mathcal{CCR}, \mathcal{CRC}, \mathcal{CRR}, \mathcal{RCC}, \mathcal{RCR}, \mathcal{RRC}, \mathcal{RRR}\}$$

Si estamos interesados en el número de caras de los resultados del experimento, entonces debemos definir la variable aleatoria discreta $X =$ *"número de caras obtenidas tras los tres lanzamientos de la moneda"*, de forma que a cada elemento del espacio muestral le corresponde algún
valor en el soporte $D = \{0, 1, 2, 3\}$

$$X : E \to D$$

Entonces tenemos: $X(\mathcal{CCC}) = 3$, $X(\mathcal{CCR}) = X(\mathcal{CRC}) = X(\mathcal{RCC}) = 2$, ..., $X(\mathcal{RRR}) = 0$

Las probabilidades se pueden expresar así:
$$P(X = 3) = P(\mathcal{CCC}) = 1/8$$
$$P(X = 2) = P(\mathcal{CCR},\mathcal{CRC}, \mathcal{RCC}) = 3/8$$
$$P(X = 1) = P(\mathcal{RRC},\mathcal{RCR}, \mathcal{CRR}) = 3/8$$
$$P(X = 0) = P(\mathcal{RRR}) = 0$$

## Función de masa

La **función de masa** de probabilidad $p$ es la función que asigna probabilidades a los valores de $D$ (soporte). Es decir:
$$p : D \to [0, 1], x_i \to p(x_i)$$

donde $p(x_i) = P[X = x_i]$

<ins>Ejemplo</ins>:

Sobre el ejemlo anterior, podemos definir al función de masa sobre el conjunto $D = \{0, 1, 2, 3\}$ como:
$$p(3) = \frac{1}{8}$$
$$p(2) = \frac{3}{8}$$
$$p(1) = \frac{3}{8}$$
$$p(0) = \frac{1}{8}$$

Siempre se debe cumpliar que la suma de las probabilidades de todos los posibles valores de la variable es 1: $\sum ^k _{i=1} p(x_i) = 1$

## Función de distribución

Se define **función de distribución** $F$ de una variable aleatoria discreta como:

$F : \mathbb{R} \to [0, 1], x \to F(x)$

donde $F(x) = P[X \le x]$

<ins>Ejemplo</ins>:

La función de distribución del ejemplo anterior sería:

$F(x) = P[X \leq x] = 0 \quad \text{si } x < 0$

$F(x) = P[X \leq x] = P[X = 0] = \frac{1}{8} \quad \text{si } 0 \leq x < 1$

$F(x) = P[X \leq x] = P[X \leq 1] = \frac{1}{8} + \frac{3}{8} = \frac{4}{8} \quad \text{si } 1 \leq x < 2$

$F(x) = P[X \leq x] = P[X \leq 2] = \frac{1}{8} + \frac{3}{8} + \frac{3}{8} = \frac{7}{8} \quad \text{si } 2 \leq x < 3$

$F(x) = P[X \leq x] = P[X \leq 3] = \frac{1}{8} + \frac{3}{8} + \frac{3}{8} + \frac{1}{8} = \frac{8}{8} = 1 \quad \text{si } x \geq 3$

## Momentos

### Esperanza $E[X]$

*Medida de localización*

$E [X] = \sum ^k _{i=1} x_i  p(x_i)$

donde ${x_1, ..., x_k}$ es el soporte de X y $p$ es la función de masa

Propiedades:

$E[aX+bY]=aE[X]+bE[Y]$

### Varianza $V[X]$

*Medida de dispersión*

$V[X] = \sum ^k _{i=1} (x_i - E[X])^2p(x_i) = E[X^2] - (E[X]^2)$

Propiedades:

- La varianza siempre es no negativa
- Se cumple:
    
    $V[aX + b] = a^2V[X]$

    donde a y b son dos constantes

### Desviación típica

*Medida de dispoersión*

$DT[X] = \sqrt{V[X]}$

Propiedades:

$DT[aX + b] = |a|DT[X]$

## Modelos notables discretos

### Distribución de Bernoulli

Una variable aleatoria con distribución de Bernoulli solo puede tomar dos valores: "éxito" y "fracaso"

$X = \begin{cases} 
1 & \text{con probabilidad } p \\ 
0 & \text{con probabilidad } 1 - p 
\end{cases}
$

donde:
- $p = P("éxito")$
- $1 - p = P("fracaso")$

Se denota como: $X \sim Ber(p)$

La función de distribución es:

$F(X) = \begin{cases} 
0 & \text{si } x \lt 0\\ 
1 - p & \text{si } 0 \le x \lt 1\\ 
1 & \text{si } x \ge 1 
\end{cases}
$

Los principales momentos de $X$ son:

$E[X] = p$

$E[X^2] = p$

$Var[X] = p(1 - p)$

### Distribución binomial

Se utiliza la distribución binomial para modelizar el número de "éxitos" tras realizar varios experimentos de Bernoulli. Se debe considerar:
- Se lleva a cabo una cantidad de repeticiones independientes $n$
- El experimeto tiene dos posibles resultados ("éxito" y "fracaso")
- La probabilidad de éxito $p$ es la misma en cada repetición del experimento

Se deonta como: $X \sim B(n, p)$

La función de masa es:

$p(x) = P(X = x) = \binom{n}{x} p^x (1-p)^{n-x}$

Esperanza y varianza son:
- $E[X] = np$
- $Var[X] = np(1 - p)$

### Distribución geométrica

Si la variable aleatoria $X$ se define como *"número de experimentos de Ber. hasta el primer éxito"*, sigue una distribución geométrica de parámetro p. Se denota como: $X \sim Ge(p)$

La función de masa es: $p(x) = p(1 - p)^{x-1}$

Nota: la 'p' de $p(x)$ del miembro izquierdo de la igualdad no es el parámetro $p = P(x = x)$

Esperanza y varianza son:
- $E[X] = \frac{1}{p}$
- $Var[X] = \frac{1 - p}{p^2}$

### Distribución de Poisson

Una variable aleatoria X sigue una distribución de Poisson de parámetro $\lambda \gt 0$ si su función de masa es:

$p(x) = \frac{\mathrm{e}^{-\lambda} \lambda ^ x}{x!}$

Esperanza y varianza son:

$E[X] = Var[X] = \lambda$

### Leyes de los grandes números

Si $X \sim B(n, p)$ def orma que $n$ es grande y $p$ es pequeña, se puede aproximar la distribución binomial por la distribución de Poisson. La aproximación es buena cuando $n \ge 30$ y $p \le 0.1$

Hay que tomar $\lambda = np$