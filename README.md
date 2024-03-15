# Markov Chain Monte Carlo (MCMC) Sampling Algorithms

*[3/15/24 Update] Uploaded notebooks for random-walk MH and MALA*

This repo contains implementations for various MCMC sampling algorithms purely intended for educational purposes. 

The general idea is that ergodic Markov chains with transition distributions that follow the detailed balance condition will eventually converge to their unique stationary distributions. If we choose the transition distribution such that the target distribution we wish to emulate is the stationary distribution of the Markov chain, then sampling directly from the Markov chain is asymptotically the same as sampling from the target distribution. 

Note that despite my simple example of e^x as the target distribution in MH and MALA, MCMC sampling will work for unnormalized probability distributions due to the intractable normalization constant cancelling out in one ratio or another.

by **Elliot H Ha**. Duke University

---

## Dependencies
- Jupyter Notebook
- PyTorch

## Project Structure
`algorithms/` is the main folder containing the implementations for both Metropolis-Hastings and MALA. 

In the future, as I add more algorithms, I plan to make this repository more modular, converting the Jupyter notebook files into regular Python files for abstraction. For now, as there are only two files, the raw notebook files are simply uploaded.

## Example Sampling Results

Both Metropolis-Hastings & MALA were run for 20,000 iterations, with a burn-in of 10,000 iterations. Ideally, the learned markov chain distribution is the target distribution, in this case, e^x. For MH, it appears we did not converge fully to the stationary distribution for the markov chain, resulting in a graph differing from e^x. I believe this to be the result of an overlooked error somewhere in dealing with log probabilities. On the other hand, MALA appears to have converged completely and correctly.

### Metropolis-Hastings sampling results for e^x
![Example sampling results for MH](/examples/mh_sampling.png)

### MALA sampling results for e^x
![Example sampling results for MALA](/examples/mala_sampling.png)

---

## References
1. Matthew Stephens' blog post on Metropolis-Hastings | [link](https://stephens999.github.io/fiveMinuteStats/MH_intro.html)
2. Tommaso Rigon's lecture notes on MALA | [link](https://tommasorigon.github.io/CompStat/slides/un_B2.pdf)
