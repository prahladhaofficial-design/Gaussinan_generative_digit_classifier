# A1


Project 1: Calculations and Derivations
Prahladha P
1. Parameter Estimation for Multivariate Gaussian
Let K = {2, 4, 7} be the set of classes. For each k  K, data are D = {x(k), . . . , x(k)}, with
k 1 N
k
x(k)  R784.
i
We are given that x(k) are iid samples from a 784-dimensional Gaussian:
i
x | (y = k)  N ( ,  )
k k
1(a) Maximum Likelihood Estimation (MLE)
Step 1: Write the Likelihood
The probability density for a d-variate normal:
(cid:18) (cid:19)
1 1
p(x |  ,  ) = exp  (x   )T 1(x   )
k k (2)d/2| |1/2 2 k k k
k
For N iid samples, the likelihood is
k
N
(cid:89)k
L( ,  ) = p(x(k) |  ,  )
k k i k k
i=1
Step 2: Log-Likelihood
l( ,  ) = log L( ,  )
k k k k
N
(cid:88)k
= log p(x(k) |  ,  )
i k k
i=1
N d N
k k
=  log(2)  log | |
k
2 2
N
1 (cid:88)k
 (x(k)   )T 1(x(k)   )
2 i k k i k
i=1
Step 3: MLE for the Mean
k
Take the derivative of log-likelihood with respect to  :
k
N N
l (cid:88)k (cid:88)k
= 1(x(k)   ) = 1 (x(k)   )
 k i k k i k
k
i=1 i=1
Set to 0 for maximum:
N N
(cid:88)k (cid:88)k
(x(k)   ) = 0 = N  = x(k)
i k k k i
i=1 i=1
1


N
1 (cid:88)k
MLE = x(k)
k N i
k
i=1
Step 4: MLE for the Covariance
k
Take the derivative of log-likelihood with respect to  :
k
(cid:34) (cid:35)
N
l N 1 (cid:88)k
=  k 1 + 1 (x(k)   )(x(k)   )T 1
 2 k 2 k i k i k k
k
i=1
Define
N
(cid:88)k
S = (x(k)   )(x(k)   )T
k i k i k
i=1
Setting to zero, and after simplification:
1
N  = S = MLE = S
k k k k N k
k
N
1 (cid:88)k
MLE = (x(k)  MLE)(x(k)  MLE)T
k N i k i k
k
i=1
Step 5: Is the Estimate Unbiased?
The sample mean MLE is unbiased.
k
The MLE (with denominator N ) is a biased estimator; the unbiased sample covariance divides
k k
by N  1:
k
N
1 (cid:88)k
unbiased = (x(k)  MLE)(x(k)  MLE)T
k N  1 i k i k
k
i=1
1(b) MAP Estimate with Gaussian Prior on
k
Assume a prior:   N ( , 1) and no prior on  .
k 0 k
The posterior is:
p( | D ,  )  p(D |  ,  )  p( )
k k k k k k k
The negative log-posterior (cost function):
N
1 (cid:88)k 1
L( ) = (x(k)   )T 1(x(k)   ) + (   )T (   )
k 2 i k k i k 2 k 0 k 0
i=1
Take the derivative and set to 0:
N
(cid:88)k
0 = 1 (x(k)   ) + (   )
k i k k 0
i=1
(cid:32) (cid:33)
N
(cid:88)k
= 1 x(k)  N  + (   )
k i k k k 0
i=1
N
(cid:88)k
N 1 +  = 1 x(k) +
k k k k k i 0
i=1
2


N
(cid:0) N 1 +  (cid:1) MAP = 1
(cid:88)k
x(k) +
k k k k i 0
i=1
(cid:32) (cid:33)
N
MAP = (cid:0) N 1 +  (cid:1)1 1
(cid:88)k
x(k) +
k k k k i 0
i=1
If  = 2I and  = I,  = 0:
k 0
N
MAP = k MLE
k N + 2 k
k
Covariance: With no structured prior, set as the MLE or unbiased estimate:
MAP = MLE or unbiased
k k k
1(c) Sampling Procedure
For each class k, generate synthetic data points as:
MLE: x  N (MLE, MLE)
new k k
MAP: x  N (MAP , MAP )
new k k
Key Estimator Formulas:
N
1 (cid:88)k
MLE = x(k)
k N i
k
i=1
N
1 (cid:88)k
MLE = (x(k)  MLE)(x(k)  MLE)T
k N i k i k
k
i=1
N
1 (cid:88)k
unbiased = (x(k)  MLE)(x(k)  MLE)T
k N  1 i k i k
k
i=1
(cid:32) (cid:33)
N
MAP = (cid:0) N 1 +  (cid:1)1 1
(cid:88)k
x(k) +
k k k k i 0
i=1
3
