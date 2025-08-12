## Discrete Probability Distribution
* Takes finite number of values $x \in \mathbb{N}$

Probability mass function (pmf)
* $f(x_i) \geq 0 \forall i$
* $\sum_{i=1}^N f(x_i = 1)$
* $P(x = a) = f(a)$


## Continuous Probability Distribution
* Takes value in a continuous space $x\in\mathbb{R}$

Probability density function (pdf)
* $f(x) \geq 0\forall x$ non-negative
* $\int_{-\infty}^\infty f(x) dx = 1$ integrates to 1
* $P(x = a) = 0$
* $P(a < x < b) = \int_a^b f(x) dx$


## Softmax Function
$$
\sigma(\mathbf{z})_i = \frac{e^{\beta z_i}}{\sum_{j=1}^K e^{\beta z_j}}
$$


## Dirac Delta Function
$$
\delta(x) = \lim_{a\rightarrow 0}\frac{1}{\sqrt{2\pi a^2}}e^{-\big(\frac{x}{2a^2}\big)^2}
$$
Has an infinitely high peak but still integrates to 1

## Spike train
$$
S(a) = \sum_i \delta(t - t_i)
$$

$\int_{t_a}^{t_b} S(t) dt =$ the spike counts during interval $[t_a, t_b]$


## Joint Distribution
$$
P(x, y)
$$
$$
\int\int P(x, y)dx dy = 1
$$

## Marginalization
$$
P(x) = \int P(x, y)dy
$$

## Conditional densities
$$
P(y | x) - \frac{P(x, y)}{P(x)}
$$
*slicing* at some value of $x$

## Independence
$$
P(x, y) = P(x)P(y) \quad\text{equivalent to}\quad P(y|x) = P(y)
$$

## Correlation vs Dependence
$$
\text{corr}(x, y) = \frac{\mathbb{E}[(x - \bar{x})(y - \bar{y})]}{\sqrt{\text{var}(x)\text{var}(y)}}
$$

## Gaussian Distribution
$$
f(x) = \frac{1}{\sqrt{2\pi \sigma^2}}\exp\Bigg(-\frac{(x-\mu)^2}{2\sigma^2}\Bigg)
$$
* $\sigma^2$ is the variance
* $\mu$ is the mean

## CLT
* The sum of many iid RVs is Gaussian, regardless of their original distibution
* Connection to repeated convolution, diffusion, etc.

## Binomial distribution
* Sum of n coin flips
$$
P(k | n, p) = \begin{pmatrix}n \\ k\end{pmatrix}p^k(1 - p)^{n - k}
$$

## Standardization of Gaussian distribution
For any random variable $X \sim \mathcal{N}(\mu, \sigma^2)$ we have $X = \mu + \sigma Z$
$$
Z = \frac{X - \mu}{\sigma}
$$

## Poisson Distribubtion
* Describes the number of events occuring within a fixed interval of time or space, given that these events occur with a known constant rate and independently of the time since the last event (memoryless)

$$
P(k) = \frac{\lambda^k}{k!}e^{-\lambda}
$$

It is the limit of a binomial distribution as the number of intervals goes to infinity, and their time window gets infinitely small

## Bayes Theorem
$$
P(A | B) = \frac{P(B | A)P(A)}{P(B)}
$$
A: Parameter of the model  
B: model and data

A: Latent state  
B: behavior/neural data

A: neural activity  
B: stimulus