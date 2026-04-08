# Signal Detection and Parameter Estimation

## Statistics 101: definitions

### Bayes factor

$$
 p(m|D) = \frac{p(D|m)\,p(m)}{p(D)}
$$

* $p(m|D)$ -- probability of model $m$, given data $D$ (hard)
* $p(D|m)$ -- probability of data, given model $m$ (easier)
* $p(m)$ -- prior (prior probability of given model)
* $p(D)$ -- normalisation

### Evidence

$$
 p(D|m) = \int{\rm d}\theta\,{p(D|\theta,m)\,p(\theta|m)}
$$

* Also called **marginal likelihood**
* Integrates likelihood over all model parameters
* Penalises overly complex models (Occam factor)
* Used to compare models

### Likelihood

$$
 \mathcal{L}(\theta) = p(D|\theta,m)
$$

* Probability of observing data $D$
* Assuming model $m$ with specific parameters $\theta$
* Central quantity for parameter estimation
* Often maximise $\mathcal{L}$ or $\log\mathcal{L}$

### Posterior

$$
p(\theta|D,m)
=
\frac{p(D|\theta,m)\,p(\theta|m)}{p(D|m)}
$$

* Probability of parameters **after observing the data**
* Combines **likelihood** and **prior**
* Central quantity in **Bayesian inference**

Interpretation:

* peak → **most probable parameters**
* width → **parameter uncertainty**

### Odds ratio

Compare two models $m_1$ and $m_2$:

$$
 \frac{p(m_1|D)}{p(m_2|D)}
 =
 \frac{p(D|m_1)}{p(D|m_2)}
 \times
 \frac{p(m_1)}{p(m_2)}
$$

* Posterior odds = **Bayes factor** × **prior odds**
* Bayes factor:

$$
B_{12} = \frac{p(D|m_1)}{p(D|m_2)}
$$

* $B_{12} > 1$ favours $m_1$
* $B_{12} < 1$ favours $m_2$

### Priors

$$
p(\theta|m)
$$

* Probability distribution for parameters **before seeing the data**
* Encodes **prior knowledge or assumptions**
* Must be specified in Bayesian inference

Examples:

* **Uniform prior** — all values equally likely
* **Log prior** — equal probability per decade
* **Informative prior** — based on previous measurements

---

### Frequentist vs Bayesian (signal searches)

#### Frequentist

* Parameters $\theta$ are **fixed but unknown**
* Data are random realisations of noise

Parameter estimation: maximise **likelihood** (or related statistic)

Detection:

* compare **null hypothesis** (noise) with signal model
* compute **test statistic** → obtain **p-value**

Decision rule:

$$
p < p_{\rm thresh}
$$

(e.g. $5\sigma$ significance)

#### Bayesian

* Parameters $\theta$ are **random variables**
* incorporate **prior information**

Parameter estimation:

* use **posterior distribution**

Model comparison:

* compare **evidences** using the **Bayes factor**

---

### $\chi^2$ likelihood (Gaussian noise)

For data vector $\mathbf{d}$ and model prediction $\mathbf{m}(\theta)$:

$$
\chi^2 =
(\mathbf{d}-\mathbf{m})^{T}
C^{-1}
(\mathbf{d}-\mathbf{m})
$$

Likelihood:

$$
p(D|\theta,m)
\propto
\exp\!\left(-\frac{1}{2}\chi^2\right)
$$

* $C$ - **noise covariance matrix**
* Includes correlations between data points

Special case: uncorrelated Gaussian noise

$$
\chi^2 =
\sum_i
\frac{(d_i - m_i)^2}{\sigma_i^2}
$$

---
---

## Finding signals

### Matched filter and signal-to-noise ratio (SNR)

Method for detecting a **known signal shape** in noise.

Inner product (overlap function):

$$
(a|b) =
a^T C^{-1} b
$$

* $C$ - noise covariance matrix $\approx\sigma^2$
* weights data by **inverse noise power**

For constant uncorrelated noise:

$$
(a|b) =
\vec{a}\cdot\vec{b} / \sigma^2
$$

Matched filter output:

$$
z = (d|s)
$$

* $d$ - data
  * Assumed to be signal + noise:
  * $d = s + n$
* $s$ - template signal
* $s = A \bar s$
  * Only is cases where signal is _linear_ in amplitude (most cases)
  * $\bar s$ is _shape_ of signal, $A$ is amplitude

Interpretation:

* **weighted correlation** of data with expected signal
* Overlap of signal and data

Signal-to-noise ratio:

$$
\rho =
\frac{(d|s)}{\sqrt{(s|s)}}
= \frac{(d|\bar s)}{\sqrt{(\bar s|\bar s)}}
$$

* normalised matched-filter output
* **dimensionless detection statistic**

Expected SNR for true signal:

$$
\rho_{\rm exp}^2 = (s|s)
$$

Optimality:

* matched filter **maximises SNR** in Gaussian noise

Detection:

* candidate signal if

$$
\rho > \rho_{\rm thresh}
$$

Typical thresholds:

* $\rho \sim 5$–$10$ depending on background and number of trials

---

#### Matched filter / SNR (brief derivation)

Assume additive noise:

$$
d = A h + n
$$

Gaussian likelihood, noise with covariance $C$:

$$
p(d|A) \propto \exp\!\left[-\frac12(d-Ah)^T C^{-1}(d-Ah)\right]
$$

Maximise $\ln p(d|A)$ w.r.t. $A$:

$$
\ln p(d|A) = \text{const} - \frac12(d-Ah|d-Ah)
$$

Expand:

$$
(d-Ah|d-Ah) = (d|d) - 2A(d|h) + A^2(h|h)
$$

Differentiate and set to zero:

$$
\frac{\partial}{\partial A}\Big[(d|d) - 2A(d|h) + A^2(h|h)\Big]=0
$$

$$
-2(d|h) + 2A(h|h)=0
\quad\Rightarrow\quad
\hat A = \frac{(d|h)}{(h|h)}
$$

Define the matched-filter (amplitude) statistic:

$$
z = (d|h)
$$

Normalise by its noise RMS to get SNR:

Under noise-only ($d=n$),

$$
\langle z \rangle = 0,
\qquad
{\rm Var}(z)=\langle (n|h)^2\rangle = (h|h)
$$

So

$$
\rho = \frac{z}{\sqrt{(h|h)}} = \frac{(d|h)}{\sqrt{(h|h)}}
$$

* matched filter: compute $(d|h)$ (noise-weighted correlation)
* SNR: matched filter output in units of its noise standard deviation

---

### Template searches

Signal parameters unknown → search over templates:

$$
s(t;\theta_k)
$$

Procedure:

1. Generate **template bank**
2. Compute **matched filter** for each template
3. Find **maximum SNR**

* Candidate signals correspond to **large peaks in SNR**
  * Either have a threshold for how large we consider as the trigger
  * Or find the largest in a data set, investigate, etc.

---

### Parameter estimation

Signal model:

$$
s(t;\theta)
$$

with parameters

$$
\theta = \{\theta_1,\theta_2,\dots\}
$$

Goal:

* find parameters that **best match the data**

Statistic to maximise:

$$
\mathcal{L}(\theta) = p(D|\theta)
,\quad \rho(\theta),\quad\text{etc.}
$$

Interpretation:

* parameters that **maximise the detection statistic**
* give the **best-fit signal model**

#### Special case: unknown amplitude

If the signal has the form

$$
s(t) = A\,\bar s(t)
$$

then the best-fit amplitude can be found analytically:

$$
\hat A =
\frac{(d|\bar s)}{(\bar s|\bar s)}
$$

So the **matched filter automatically finds the optimal amplitude**.

---

#### Estimating uncertainty

Uncertainty may determined by the **shape of the likelihood peak** around the best-fit parameters.

* Very sharp peak: low uncertainty in best-fit value
* Very narrow peak: high uncertainty

Approximate rule:

$$
\Delta\chi^2 \sim 1
$$

gives the **$1\sigma$ uncertainty** on a parameter.

Key idea:

* sharper peak in likelihood → **smaller uncertainty**
* uncertainty typically scales as

$$
\sigma_\theta \propto \frac{1}{\text{SNR}}
$$
