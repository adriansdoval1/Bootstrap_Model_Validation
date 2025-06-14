# Bootstrap Model Validation

The Bootstrapping methodology is a resampling technique used for statistical inference. It is based on creating a new sample (from our original observed sample) in order to make an estimate about population statistics (understanding "statistic" as a function of some population parameter, i.e., θ = t(P)).

The general idea of Bootstrapping can be summarized as follows: The population is to the sample as the sample is to the subsample.

Let us suppose we draw a sample S = {X₁, ..., Xₙ} from a population P = {x₁, ..., x_N}, and we are interested in estimating a population parameter, say θ = t(P) (this parameter can be a vector).

To make inference about the aforementioned population parameter, a subsample with replacement is created based on S, which we will call a Bootstrap sample, denoted S₁*. Some alternative methods suggest that this new sample should be created in the same way the original sample was created; however, the macro implemented creates the subsample using the Simple Random Sampling with Replacement method, which means that each element of sample S has the same probability of being selected (the exact probability is 1/n), and each element can be chosen more than once.

The creation of this new subsample is replicated b times; the b-th Bootstrap sample is denoted S_b*.

The population parameter is estimated using each of the Bootstrap samples:
T_b* = t(S_b*)

The distribution of T_b* for estimating T is analogous to the distribution of T for estimating θ.

With the parameter T_b*, an estimate for the population parameter can be generated.

When applied in terms of Generalized Linear Models (GLMs), the technique follows the algorithm described below.

