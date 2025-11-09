# Options-Pricing-with-Longstaff-Schwartz

This notebook implements **option pricing using the Least Squares Monte Carlo (LSM) method** (from the Longstaff-Schwartz algorithm). It simulates **Geometric Brownian Motion (GBM)** paths, computes **exercise values**, and estimates **continuation values** through **regression fitting**.

* **GBM simulation** for the underlying asset
* **Exercise value computation** for an American-style payoff
* **Continuation value estimation** via regression (implied in the code)
* **Backward induction** to estimate optimal exercise strategy and option price


## 📘 Longstaff Schwartz - Least Squares Monte Carlo Option Pricing

### Overview

This notebook implements and visualizes the **Longstaff–Schwartz (LSM)** method for pricing **American options** using **Monte Carlo simulation** and **least squares regression**.

The method allows estimating the optimal exercise strategy for American-style derivatives by combining simulated price paths and regression-based continuation value estimation.

---

### 🔬 Methods Implemented

#### 1. **Geometric Brownian Motion (GBM) Simulation**

* Simulates the underlying asset price ( X_t ) using:
  [
  dX_t = \mu X_t dt + \sigma X_t dW_t
  ]
* Parameters: drift ( r ), volatility ( \sigma ), time horizon ( T ), and number of steps ( n ).
* Generates multiple sample paths to represent stochastic asset dynamics.

#### 2. **Option Payoff Function**

* Example payoff for a put option:
  [
  \text{Exercise Value} = \max(K - X_t, 0)
  ]
* The notebook visualizes in-the-money (ITM) vs. out-of-the-money paths.

#### 3. **Continuation Value Estimation**

* For each time step (moving backward in time), regression is used to approximate the conditional expectation of discounted future payoffs.
* This is the “least squares” step of the LSM method.

#### 4. **Backward Induction**

* Iteratively compares **exercise value** vs. **continuation value**.
* Determines optimal early exercise points.
* Estimates the fair option price as the discounted average of simulated cashflows under the optimal policy.

---

### 📊 Visualizations

The notebook includes:

* Path simulation plots (showing ITM vs OTM regions)
* Scatter plots of discounted cashflows vs. underlying price
* Regression fit curves for continuation value approximation

---

### 🧰 Dependencies

```bash
pip install numpy matplotlib ipywidgets aleatory
```
