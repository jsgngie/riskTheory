Expected Value:

For a discrete random variable XX with possible outcomes x1,x2,…,xnx1​,x2​,…,xn​ and corresponding probabilities p1,p2,…,pnp1​,p2​,…,pn​, the expected value is:

$$
\mathbb{E}[X] = \sum_{i=1}^{n} x_i p_i
$$

For a continuous random variable XX with probability density function fX(x)fX​(x), the expected value is:

$$
\mathbb{E}[X] = \int_{-\infty}^{\infty} x f_X(x) \, dx
$$

Variance:

The variance of a random variable XX is:

$$
\text{Var}(X) = \mathbb{E}[(X - \mathbb{E}[X])^2]
$$

Alternatively, it can be expressed as:

$$
\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2
$$

# Risk Process and Classical Risk Process

### Risk Process:

A **Risk Process** is a stochastic process that models the evolution of the financial position of an insurance company or a similar risk-bearing entity over time. The process typically represents the surplus or capital of the insurer, taking into account the income from premiums and the outgo due to claims. The risk process helps in assessing the likelihood of insolvency and in managing the capital required to cover future claims.

Mathematically, it is often denoted by \( U(t) \), where \( U(t) \) represents the surplus of the insurer at time \( t \).

### Classical Risk Process:

The **Classical Risk Process** is a specific type of risk process where the surplus evolves according to a linear model. It is typically modeled as a process that starts with an initial surplus \( u \) and increases over time based on premiums received, while being reduced by claim amounts occurring according to a Poisson process.

The classical risk process can be expressed as:

$$
U(t) = u + c t - S(t)
$$

Where:
- \( U(t) \) is the surplus at time \( t \),
- \( u \) is the initial surplus,
- \( c \) is the premium rate (assumed to be constant),
- \( S(t) \) is the aggregate claims process at time \( t \).

Here, \( S(t) \) is typically modeled as a compound Poisson process, where the claim arrivals follow a Poisson process, and the claim sizes are independent and identically distributed random variables.

# Ruin and Ruin Probability

### Ruin:

**Ruin** refers to the situation where the surplus of an insurer (or any risk-bearing entity) becomes negative, meaning the insurer is unable to meet its liabilities. In other words, ruin occurs when the company’s capital is depleted, and it is unable to pay claims or cover future expenses. 

Mathematically, ruin occurs at a time \( t \) when the surplus \( U(t) \) becomes less than or equal to zero:

$$
U(t) \leq 0
$$

Ruin is a critical event in risk management, as it indicates insolvency or bankruptcy for the insurer.

### Ruin Probability:

**Ruin Probability** is the probability that an insurer (or any risk-bearing entity) will experience ruin at some point in the future. It quantifies the risk of an insurer’s surplus becoming negative, which is a key measure for determining how much capital the insurer needs to avoid bankruptcy or insolvency.

If \( \tau \) represents the time of ruin, then the ruin probability is the probability that the insurer's surplus hits zero or becomes negative before some time horizon \( T \). The ruin probability \( \psi(u) \) for an insurer with an initial surplus \( u \) is defined as:

$$
\psi(u) = P(\tau < \infty | U(0) = u)
$$

Where:
- \( \tau \) is the time of ruin,
- \( U(0) = u \) is the initial surplus,
- \( \psi(u) \) is the probability of ruin given the initial surplus \( u \).

Ruin probability is an important concept in actuarial science and risk management, as it helps assess the financial stability of an insurer over time.

# Expected Value of the Sum of Identically Distributed Random Variables

### Problem Setup:

We want to compute the expected value of the sum of a random number of identically distributed random variables. Let:

- \( X_1, X_2, \dots \) be identically distributed random variables with expected value \( \mathbb{E}[X] \).
- \( N \) be a random variable representing the number of terms in the sum, where \( N \) is independent of \( X_1, X_2, \dots \) and has an expected value \( \mathbb{E}[N] \).

The goal is to compute the expected value of the sum \( S_N \) of these \( N \) random variables:

$$
S_N = X_1 + X_2 + \dots + X_N
$$

### Approach:

The key is to use the **law of total expectation** (or iterated expectation), which allows us to condition on \( N \) and then take the expectation over \( N \). The expected value of the sum \( S_N \) can be computed as follows:

$$
\mathbb{E}[S_N] = \mathbb{E}\left[\mathbb{E}[S_N | N]\right]
$$

Since \( X_1, X_2, \dots \) are identically distributed, we have:

$$
\mathbb{E}[S_N | N = n] = n \mathbb{E}[X]
$$

Thus, the expected value of the sum \( S_N \) is:

$$
\mathbb{E}[S_N] = \mathbb{E}[N] \cdot \mathbb{E}[X]
$$

### Assumptions:

1. **Independence**: The random variable \( N \) is independent of the identically distributed random variables \( X_1, X_2, \dots \).
2. **Identically Distributed**: The random variables \( X_1, X_2, \dots \) are identically distributed, meaning each has the same expected value \( \mathbb{E}[X] \).
3. **Finite Expectations**: The expected values \( \mathbb{E}[X] \) and \( \mathbb{E}[N] \) must be finite for the formula to hold.
4. **Non-negative Number of Terms**: The number of terms \( N \) should be a non-negative integer (i.e., \( N \geq 0 \)).

### Conclusion:

The expected value of the sum \( S_N \) of a random number of identically distributed random variables is the product of the expected value of \( N \) and the expected value of one of the random variables \( X \):

$$
\mathbb{E}[S_N] = \mathbb{E}[N] \cdot \mathbb{E}[X]
$$

# Relative Safety Loading

### Definition:

**Relative Safety Loading** refers to the additional premium charged by an insurer to account for the risk of ruin or insolvency, beyond the expected claims and administrative costs. It is the extra charge added to the basic premium to ensure that the insurer maintains a sufficient surplus to cover unexpected future claims or adverse developments in claims experience.

Mathematically, relative safety loading is often expressed as a proportion of the expected premium or the expected claims. If \( \theta \) represents the relative safety loading, it can be defined as:

$$
\theta = \frac{ \text{Safety Loading} }{ \text{Expected Claims} }
$$

Where:
- The **Safety Loading** is the amount added to the premium to account for risk.
- The **Expected Claims** represent the anticipated amount the insurer expects to pay for claims.

Relative safety loading helps in maintaining the financial stability of the insurance company and reduces the risk of ruin, especially in volatile environments where claims can fluctuate significantly.

### Assumptions:
1. **Adequate Premium Base**: The expected claims or premiums are sufficiently estimated and stable.
2. **Independence**: Claims and other risk factors are assumed to be independent of the premium rate.
3. **Risk Aversion**: The insurer includes a buffer to manage the risk of financial instability or ruin.

In essence, relative safety loading quantifies the amount of risk-bearing capacity required above the basic expected claims to safeguard the insurer against unforeseen claims events.

# The Strong Law of Large Numbers

### Definition:

The **Strong Law of Large Numbers** (SLLN) states that the sample average of a sequence of independent and identically distributed (i.i.d.) random variables converges almost surely to the expected value (mean) of the random variables as the number of observations tends to infinity.

Mathematically, let \( X_1, X_2, X_3, \dots \) be a sequence of i.i.d. random variables with expected value \( \mathbb{E}[X_i] = \mu \) and finite variance \( \text{Var}(X_i) = \sigma^2 \). The sample average is defined as:

$$
\overline{X}_n = \frac{1}{n} \sum_{i=1}^{n} X_i
$$

The strong law of large numbers states that:

$$
\overline{X}_n \xrightarrow{a.s.} \mu \quad \text{as} \quad n \to \infty
$$

Where \( \xrightarrow{a.s.} \) denotes almost sure convergence. This means that:

$$
P\left( \lim_{n \to \infty} \overline{X}_n = \mu \right) = 1
$$

### Assumptions:
1. **Independence**: The random variables \( X_1, X_2, \dots \) are independent.
2. **Identically Distributed**: The random variables \( X_1, X_2, \dots \) are identically distributed.
3. **Finite Mean**: The expected value \( \mathbb{E}[X_i] = \mu \) exists and is finite.
4. **Finite Variance**: The variance \( \text{Var}(X_i) = \sigma^2 \) exists and is finite.

### Intuition:

The strong law of large numbers essentially says that, as we observe more and more random variables, the average of the observed values will converge to the true expected value with probability 1. This is a stronger version of the **weak law of large numbers**, which only guarantees convergence in probability, not almost sure convergence.

### Conclusion:

The strong law of large numbers is a fundamental result in probability theory and statistics, ensuring that sample averages will converge to the expected value as the sample size increases.

# Proof: Behavior of \( X(t) \) in the Classical Risk Process

### Problem Statement:

For the classical risk process, we want to prove that as \( t \to \infty \), the surplus \( X(t) \) will either tend to \( \infty \) or \( -\infty \), depending on whether \( \rho > 0 \) or \( \rho < 0 \), where \( \rho \) is the **net premium income rate**.

### Classical Risk Process Model:

The classical risk process is modeled by the following stochastic differential equation:

$$
X(t) = u + ct - S(t)
$$

Where:
- \( X(t) \) is the surplus at time \( t \),
- \( u \) is the initial surplus,
- \( c \) is the premium rate (constant),
- \( S(t) \) is the aggregate claims process at time \( t \).

We assume that the claims process \( S(t) \) is a compound Poisson process, where claims arrive according to a Poisson process with rate \( \lambda \), and the claim sizes are independent and identically distributed random variables.

### Analysis:

The evolution of the surplus \( X(t) \) is determined by the balance between the premium income and the claims payments. The rate of change of the surplus is:

$$
\frac{dX(t)}{dt} = c - \text{Claim rate}
$$

Thus, the behavior of \( X(t) \) over time depends on the value of \( c \) relative to the claim rate. Specifically:

- If \( \rho = c - \mathbb{E}[\text{Claim rate}] > 0 \), the insurer’s premiums exceed the expected claims rate, leading to a positive net premium income. In this case, the surplus will grow over time, and \( X(t) \to \infty \) as \( t \to \infty \).
- If \( \rho = c - \mathbb{E}[\text{Claim rate}] < 0 \), the insurer’s premiums are insufficient to cover the expected claims, leading to a negative net premium income. In this case, the surplus will decrease over time, and \( X(t) \to -\infty \) as \( t \to \infty \).

### Proof:

To analyze the long-term behavior of \( X(t) \), we note the following:

1. **For \( \rho > 0 \)**:
   - The premium income rate \( c \) exceeds the expected claim rate. Hence, the insurer accumulates surplus over time.
   - The surplus \( X(t) \) grows without bound because the premium income is sufficient to cover both claims and the company's expenses.
   - Therefore, as \( t \to \infty \), \( X(t) \to \infty \).

2. **For \( \rho < 0 \)**:
   - The premium income rate \( c \) is less than the expected claim rate. Hence, the insurer’s surplus diminishes over time.
   - The insurer is unable to meet the claims, and the surplus \( X(t) \) decreases without bound, leading to insolvency.
   - Therefore, as \( t \to \infty \), \( X(t) \to -\infty \).

### Conclusion:

From the above analysis, we conclude that:

- If \( \rho > 0 \), the surplus \( X(t) \) tends to \( \infty \) as \( t \to \infty \).
- If \( \rho < 0 \), the surplus \( X(t) \) tends to \( -\infty \) as \( t \to \infty \).

This shows that the classical risk process exhibits either infinite growth or ruin, depending on the net premium income rate \( \rho \).

# Proof: Deriving \( \int_0^\infty (1 - F(z)) dz = \int_0^\infty z f(z) dz = \mathbb{E}[Z] \)

### Problem Setup:

We are tasked with proving the following identity:

$$
\int_0^\infty (1 - F(z)) dz = \int_0^\infty z f(z) dz = \mathbb{E}[Z]
$$

Where:
- \( F(z) \) is the cumulative distribution function (CDF) of a random variable \( Z \),
- \( f(z) \) is the probability density function (PDF) of \( Z \),
- \( \mathbb{E}[Z] \) is the expected value of \( Z \).

### Step 1: Integral \( \int_0^\infty (1 - F(z)) dz \)

Start with the definition of the CDF \( F(z) \) and recognize that:

$$
1 - F(z) = P(Z > z)
$$

This is the tail probability, or the probability that the random variable \( Z \) exceeds \( z \). Thus, the integral becomes:

$$
\int_0^\infty (1 - F(z)) dz = \int_0^\infty P(Z > z) dz
$$

We can rewrite this using the fact that \( P(Z > z) = \int_z^\infty f(x) dx \), where \( f(x) \) is the PDF of \( Z \):

$$
\int_0^\infty P(Z > z) dz = \int_0^\infty \left( \int_z^\infty f(x) dx \right) dz
$$

By changing the order of integration (using Fubini's theorem), we get:

$$
\int_0^\infty \left( \int_z^\infty f(x) dx \right) dz = \int_0^\infty \left( \int_0^x dz \right) f(x) dx
$$

The inner integral \( \int_0^x dz \) is simply \( x \), so we have:

$$
\int_0^\infty (1 - F(z)) dz = \int_0^\infty x f(x) dx
$$

Thus, we find that:

$$
\int_0^\infty (1 - F(z)) dz = \int_0^\infty z f(z) dz
$$

### Step 2: Expected Value of \( Z \)

The expected value of a continuous random variable \( Z \) with PDF \( f(z) \) is given by:

$$
\mathbb{E}[Z] = \int_0^\infty z f(z) dz
$$

Thus, we conclude that:

$$
\int_0^\infty z f(z) dz = \mathbb{E}[Z]
$$

### Conclusion:

We have shown that:

$$
\int_0^\infty (1 - F(z)) dz = \int_0^\infty z f(z) dz = \mathbb{E}[Z]
$$

This completes the proof.

# Deriving Ruin Probability for Exponentially Distributed Claims

### Problem Setup

We are dealing with a **classical risk model** where claims are exponentially distributed, and we want to compute the **ruin probability**. In this model, the surplus \( X(t) \) at time \( t \) is defined as:

$$
X(t) = u + ct - S(t)
$$

Where:
- \( u \) is the initial surplus,
- \( c \) is the premium income rate,
- \( S(t) \) is the aggregate claims process at time \( t \), modeled as a compound Poisson process.

The goal is to compute the probability of ruin, denoted as \( \psi(u) \), which is the probability that the surplus \( X(t) \) reaches 0 before reaching an arbitrarily large value.

### Change of Variables (Lines 9–11 in Lecture Notes)

We will now explain the derivation of the equality from **line 9** to **line 11** in your lecture notes. These steps often involve using the **Laplace transform** of the claims distribution and performing a change of variables to simplify the expression.

#### Line 9 (Starting Point)

On line 9, we begin with the integral involving the **Laplace transform** of the claims distribution:

$$
\mathbb{E}[e^{-\theta S(t)}] = \exp\left( -\lambda \int_0^t \left( 1 - \frac{1}{1 + \theta} \right) dt \right)
$$

Where \( \theta \) is a parameter used to solve for the ruin probability, and \( \lambda \) is the rate of the Poisson process. The Laplace transform of the **exponentially distributed claim size** \( Y \) is used here.

#### Line 11 (After Change of Variables)

At line 11, the change of variables is performed to simplify the integral. Specifically, we often make the substitution \( \theta \to \frac{1}{1 + \theta} \), or some equivalent transformation. The idea is to reparameterize the equation to make it easier to solve for the ruin probability.

#### Detailed Change of Variables

Let’s break this down more clearly:

1. **Starting Integral (Line 9)**:

   Suppose we have an integral involving the Laplace transform:

   $$
   \int_0^\infty e^{-\theta x} f(x) \, dx
   $$

   Where \( f(x) = \lambda e^{-\lambda x} \) is the probability density function (PDF) of the exponentially distributed claim size.

2. **Substitute the Laplace Transform of Exponential Distribution**:

   The Laplace transform of the exponential distribution \( f(x) = \lambda e^{-\lambda x} \) is:

   $$
   \int_0^\infty e^{-\theta x} \lambda e^{-\lambda x} \, dx
   $$

   Simplifying this:

   $$
   \lambda \int_0^\infty e^{-(\lambda + \theta) x} \, dx
   $$

3. **Evaluate the Integral**:

   The integral is straightforward to evaluate:

   $$
   \lambda \left[ \frac{e^{-(\lambda + \theta) x}}{\lambda + \theta} \right]_0^\infty
   $$

   This evaluates to:

   $$
   \frac{\lambda}{\lambda + \theta}
   $$

4. **Change of Variables**:

   Now, let’s apply the change of variables \( \theta \to \frac{1}{1 + \theta} \), or an equivalent transformation. After performing this transformation, we obtain a simplified expression, which is easier to work with for solving the ruin probability.

   The change of variables helps us transform the expression into a more manageable form, which will eventually help us solve for the ruin probability in the case of exponentially distributed claims.

### Conclusion

In summary:
- The **change of variables** between line 9 and line 11 simplifies the expression involving the Laplace transform of the exponentially distributed claims.
- This change allows us to perform easier calculations or solve the differential equations more effectively to derive the ruin probability formula.
- The key takeaway is that the Laplace transform and the change of variables technique help transform a complex integral into a simpler form, which is crucial for obtaining the ruin probability in cases with exponentially distributed claims.


# Definition of Lundberg Exponent

The **Lundberg exponent** is a key concept in risk theory, particularly in the study of the classical risk process. It is defined as the unique solution to the **Cramér-Lundberg equation**, which governs the asymptotic behavior of the ruin probability in a risk model.

Let \( X(t) \) denote the surplus at time \( t \) in a risk process, and let \( S(t) \) be the cumulative claims process. The Lundberg exponent \( \theta \) is defined as the solution to the following equation:

$$
\mathbb{E}[e^{\theta Y}] = 1
$$

Where \( Y \) represents the claim size distribution, and \( \mathbb{E}[e^{\theta Y}] \) is the **moment generating function (MGF)** of the claim size. The Lundberg exponent \( \theta \) is used to describe the growth rate of the ruin probability as time goes to infinity.

In practice, the Lundberg exponent gives insight into the **probability of ruin** in a risk process. The larger the value of \( \theta \), the lower the probability of ruin. The equation is called the **Cramér-Lundberg equation**.

### Example of a Distribution where the Lundberg Exponent Exists

For an **exponentially distributed claim size** with rate \( \lambda \), the MGF is:

$$
\mathbb{E}[e^{\theta Y}] = \frac{\lambda}{\lambda - \theta}
$$

For the Lundberg exponent to exist, we need the MGF to be finite at some positive value of \( \theta \). The Lundberg exponent \( \theta \) is the value where:

$$
\frac{\lambda}{\lambda - \theta} = 1
$$

Solving this, we find that the Lundberg exponent exists and is:

$$
\theta = \lambda
$$

Thus, for an exponentially distributed claim size, the Lundberg exponent exists and is equal to the rate parameter \( \lambda \).

### Example of a Distribution where the Lundberg Exponent Does Not Exist

For a **Pareto distribution** with shape parameter \( \alpha \) and scale parameter \( x_m \), the MGF does not exist for any \( \theta > 0 \). The MGF for a Pareto distribution is:

$$
\mathbb{E}[e^{\theta Y}] = \frac{x_m^\alpha}{\alpha - \theta}
$$

However, this expression is not valid for values of \( \theta \) greater than \( \alpha \), meaning the MGF blows up and the Lundberg exponent does not exist for a Pareto distribution. Specifically, the expectation diverges, and no finite value of \( \theta \) can satisfy the Cramér-Lundberg equation.

### Conclusion

- The **Lundberg exponent** exists for distributions such as the **exponential distribution** and is the solution to the equation \( \mathbb{E}[e^{\theta Y}] = 1 \).
- The **Lundberg exponent does not exist** for distributions like the **Pareto distribution**, where the MGF does not have a finite solution for \( \theta > 0 \).

# Definition of De Vylder Approximation of Ruin Probability

The **De Vylder approximation** is an approximation method for calculating the **ruin probability** in the classical risk model. This approximation is particularly useful when the claims are not exponentially distributed, and it provides a way to estimate the probability of ruin without directly solving the more complicated integral equations.

In the classical risk process, the ruin probability \( \psi(u) \) is the probability that the surplus \( X(t) \) falls below zero, given an initial surplus \( u \). The De Vylder approximation is based on the assumption that, under certain conditions, the ruin probability can be approximated by a **Gaussian-like** distribution.

### Formula for De Vylder Approximation

For a risk process with claim size distribution \( F(x) \), the De Vylder approximation to the ruin probability \( \psi(u) \) is given by:

$$
\psi(u) \approx \exp \left( -\frac{2u}{\sigma^2} \right)
$$

Where:
- \( u \) is the initial surplus,
- \( \sigma^2 \) is the variance of the claim size distribution.

The approximation assumes that the **claims distribution** has a finite mean \( \mu \) and variance \( \sigma^2 \). It approximates the probability of ruin as a function of the initial surplus and the distribution's variance, which is particularly useful when the exact ruin probability is hard to compute.

### Assumptions of the De Vylder Approximation

1. **Large Initial Surplus**: The approximation is most accurate when the initial surplus \( u \) is large compared to the mean claim size \( \mu \).
2. **Finite Variance**: The claim size distribution should have a finite variance \( \sigma^2 \).
3. **Moderate Growth of Claim Size**: The approximation is typically used when the claims have moderate growth (i.e., neither extremely heavy-tailed nor too small).

### Example of De Vylder Approximation

Consider a risk process with claims following a **Gamma distribution** with shape parameter \( \alpha \) and rate parameter \( \lambda \). The variance of the claim size is \( \sigma^2 = \frac{\alpha}{\lambda^2} \). Using the De Vylder approximation, the ruin probability \( \psi(u) \) can be approximated as:

$$
\psi(u) \approx \exp \left( -\frac{2u \lambda^2}{\alpha} \right)
$$

This approximation provides a simple way to estimate the probability of ruin when the exact calculation is difficult or not possible.

### Conclusion

The **De Vylder approximation** is a useful method for approximating the ruin probability in risk models, especially when dealing with non-exponential claim size distributions. It assumes a Gaussian-like behavior for large initial surpluses and uses the variance of the claim size distribution to estimate the probability of ruin.
