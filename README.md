# Cosmological parameter estimation with BAO and CMB

Teaching material for ICTS summer school in 2026. These notebooks develop practical skills in both Bayesian and
frequentist approaches to parameter inference, with an emphasis on building working implementations from scratch. 
We take the examples of CMB and BAO data, eventually working towards reproducing the results of [this paper](https://arxiv.org/pdf/2506.12004). 

---

## Course overview

Modern cosmological analyses — CMB, BAO, large-scale structure, gravitational waves,
supernovae, ++ — all reduce to the same core problem: given noisy data and a
physical model, what do the data tell us about the parameters of the Universe?

These notebooks cover two complementary families of methods:

**Bayesian inference** maps data onto a posterior probability distribution over
parameters, naturally incorporating prior knowledge and propagating
uncertainties. Bayesian MCMC (Markov chain Monte Carlo) is the dominant
framework in cosmology, underpinning codes such as [`CosmoMC`](https://cosmologist.info/cosmomc/), [`cobaya`](https://cobaya.readthedocs.io/en/latest/), and
[`MontePython`](https://github.com/brinckmann/montepython_public). 

**Frequentist methods — profile likelihoods** have been gaining significant
traction in cosmology as a cross-check on posterior-based results. The profile
likelihood traces the maximum likelihood achievable at each parameter value by
optimising over all other ("nuisance") parameters, as opposed to Bayesian 
approaches that marginalise over the other parameters. It offers complementary 
insight into the influence of priors on Bayesian posteriors.
Several profile likelihood codes are also publicly-available for use in 
conjunction with cosmological likelihoods, including [`Procoli`](https://github.com/tkarwal/procoli), [`pinc`](https://github.com/LauraHerold/pinc) and 
[`PROSPECT`](https://github.com/AarhusCosmology/prospect_public). 

Both approaches are taught here because in practice they should agree (eg. with [dynamical dark energy](https://arxiv.org/pdf/2506.12004)), and when they don't (eg. with [early dark eergy](https://arxiv.org/pdf/2401.14225)), something interesting is happening. 


---

## Software environment

All notebooks use only:

```
numpy  scipy  matplotlib  corner  tqdm
```
with some optional packages 
```
ipywidgets  ipympl
```
for interactive plots. 

Install with:

```bash
pip install numpy scipy matplotlib corner tqdm
```

or, if using conda:

```bash
conda install numpy scipy matplotlib corner tqdm
```

The easiest way to run these notebooks would be on Google colab, using the links below. 


---

## Notebooks by lecture 

| Topic | Lectures | Notebook | Colab link | Solutions |
|-------|----------------|----------|------------|-----------|
| Bayesian statistics | MCMC slides | [`write_MH_MCMC`](https://github.com/tkarwal/ICTS_summer_school/blob/main/icts_write_MH_MCMC.ipynb) | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tkarwal/ICTS_summer_school/blob/main/icts_write_MH_MCMC.ipynb) | Uploaded post lectures |
| Profile likelihoods | Profiles slides | [`write_profile_likelihood`](https://github.com/tkarwal/ICTS_summer_school/blob/main/icts_write_profile_likelihood.ipynb) | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tkarwal/ICTS_summer_school/blob/main/icts_write_profile_likelihood.ipynb) | - |
| MontePython and Cobaya demos | Samplers slides | No notebooks | - | - |


---

## Further reading

- [Original Metropolis paper](https://www.aliquote.org/pub/metropolis-et-al-1953.pdf)
- [Original Hastings paper](https://www.jstor.org/stable/2334940?seq=1)
- [Why isn't every physicist a Bayesian? ](https://www.astro.princeton.edu/~strauss/AST303/bayesian_paper.pdf)
- [Procoli implementation of profiles in cosmology](https://arxiv.org/pdf/2401.14225)
- [How to use profiles in cosmology](https://arxiv.org/pdf/2408.07700)
- [Feldman-Cousins boundary corrections](https://arxiv.org/pdf/physics/9711021)
- [Fisher matrices in cosmology](https://arxiv.org/pdf/0906.4123)


---