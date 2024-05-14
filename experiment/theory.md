The M/G/1 queueing model is a fundamental stochastic process used to analyze the behaviour of a single-server queue with general arrival and service time distributions. Here's a breakdown of its key components:

 **Arrival Process (M):**
   - The arrival process follows a Poisson distribution, where customers arrive at the system independently over time.
   - The mean arrival rate is denoted by \(\lambda\), representing the average number of arrivals per unit time.

 **Service Process (G):**
   - The service time distribution can be arbitrary and is denoted by \(G\).
   - Unlike in the M/M/1 model where service times follow an exponential distribution, in the M/G/1 model, service times can follow any general distribution.

 **Number of Servers (1):**
   - There is a single server in the system, serving customers one at a time.
   - Once a customer begins service, they are served to completion before the server moves on to the next customer.


The M/G/1 queueing model is widely applicable in various fields such as telecommunications, computer networks, and customer service systems, providing valuable insights into system performance and aiding in optimization and capacity planning.



**The Pollaczek-Khintchine Formula**

The Pollaczek-Khintchine formula is a powerful tool in queueing theory that provides insights into the expected waiting time for arriving customers in a queueing system. Let's delve into its components and implications.

**. Queue Length Contribution:**
When a customer arrives, we consider the existing queue length. Each customer ahead of her contributes, on average, to her delay by the expected service time (\(E[\text{S}]\)). With an average of \(L_q\) customers already in the queue at her arrival, her delay due to these customers is \(L_q \times E[\text{S}]\).

**. Service Time Contribution:**
Upon arrival, if the server is currently serving a customer, her delay is influenced by the remaining service time of this customer. Since the customer in service might have already spent some time being served, her delay due to this customer is based on the remaining service time, not the total service time. Generally, these two are not equal in expectation.

**. Average Queue Wait:**
The average queue wait (\(W_q\)) for an arriving customer can be expressed as:

\[ W_q = L_q \times E[\text{S}] + \text{Pr}\{\text{server busy}\} \times E[\text{residual service time} \mid \text{server busy}] \]

By using Little's Law to eliminate \(L_q\) and rearranging terms, we get:

\[ W_q = \frac{\text{Pr}\{\text{server busy}\} \times E[\text{residual service time} \mid \text{server busy}]}{1-\rho} \]

Here, \(\text{Pr}\{\text{server busy}\}\) represents the probability that the arriving customer finds the server busy, which is equivalent to the server utilization (\(\rho\)) due to the PASTA property.

**. Expected Residual Service Time:**
To find the expected residual service time conditional on the server being busy, it's shown that:

\[ E[\text{residual service time} \mid \text{server busy}] = \frac{E[\text{S}^2]}{2 \times E[\text{S}]} = \frac{1 + \text{CV}^2}{2} \times E[\text{S}] \]

Where \(\text{CV}^2\) is the squared coefficient of variation of the service distribution. This result is related to a standard result from renewal theory and is sometimes referred to as the average excess or average residual time of a renewal process.

**5. Comprehensive Formula:**
Combining the above results, the formula for \(W_q\) becomes:

\[ W_q = \frac{1 + \text{CV}^2}{2} \times \frac{\rho}{1-\rho} \times E[\text{S}] \]

This formula incorporates three terms: a variability term, a utilization term, and a time-scale term, making it a powerful tool in estimating queue wait times. Other measures of effectiveness such as \(L\), \(W\), and \(L_q\) can be easily derived from \(W_q\) using Little's Law. 

The Pollaczek-Khintchine formula requires only three parameters - arrival rate (\(\lambda\)), mean service time (\(E[\text{S}]\)), and squared coefficient of variation (\(\text{CV}^2\)) - making it practical for estimating and optimizing queueing system performance.


**Pollaczek-Khintchine Formula Equations:**

1. **Mean Number of Customers in the Queue (\(L_q\)):**
\[
\begin{aligned}
L_q &= \frac{1 + \text{CV}^2}{2} \cdot \frac{\rho^2}{1-\rho} \\
&= \frac{\lambda^2 \mathrm{E}\left[S^2\right]}{2(1-\rho)} \\
&= \frac{\rho^2 + \lambda^2 \sigma_B^2}{2(1-\rho)}
\end{aligned}
\]

2. **Mean Waiting Time in the Queue (\(W_q\)):**
\[
\begin{aligned}
W_q &= \frac{1 + \text{CV}^2}{2} \cdot \frac{\rho}{\mu - \lambda} \\
&= \frac{\lambda \mathrm{E}\left[S^2\right]}{2(1-\rho)} \\
&= \frac{\rho^2 / \lambda + \lambda \sigma_B^2}{2(1-\rho)}
\end{aligned}
\]

3. **Mean Waiting Time in the System (\(W\)):**
\[
\begin{aligned}
W &= \frac{1 + \text{CV}^2}{2} \cdot \frac{\rho}{\mu - \lambda} + \frac{1}{\mu} \\
&= \frac{\lambda \mathrm{E}\left[S^2\right]}{2(1-\rho)} + \frac{1}{\mu} \\
&= \frac{\rho^2 / \lambda + \lambda \sigma_B^2}{2(1-\rho)} + \frac{1}{\mu}
\end{aligned}
\]

4. **Mean Number of Customers in the System (\(L\)):**
\[
\begin{aligned}
L &= \frac{1 + \text{CV}^2}{2} \cdot \frac{\rho^2}{1-\rho} + \rho \\
&= \frac{\lambda^2 \mathrm{E}\left[S^2\right]}{2(1-\rho)} + \rho \\
&= \frac{\rho^2 + \lambda^2 \sigma_B^2}{2(1-\rho)} + \rho
\end{aligned}
\]

These equations provide essential insights into the performance of the queueing system, incorporating factors such as the variability of service times (\(CV\)), utilization (\(\rho\)), arrival rate (\(\lambda\)), mean service time (\(E[S]\)), and the mean square of the service time (\(E[S^2]\)). They are derived from the Pollaczek-Khintchine formula, a fundamental tool in queueing theory for analyzing and optimizing system performance.
