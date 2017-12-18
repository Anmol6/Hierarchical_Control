# Hierarchical Control

The code is built on homework 2 of Berkeley's CS 294 [course](https://www.rll.berkeley.edu/deeprlcourse)

There are two policies 
- High Level Policy: This policy receives a state as input and outputs parameters of an affine function, ie. weights W and bias b 
- Low Level Policy: This policy receives a state as input and outputs features that are input to the affine function, g_theta(s_t+k)

The action is then sampled from the vector defined by the affine function applied to the output of the low-level policy.

Now hierarchy is achieved by enforcing that the high-level policy not change for k-timesteps (a specified hyperparameter).

### Example
Read `train_pg.py` for all command line arguments. Example run:
```
python train_pg.py Hopper-v1 -e 1 -ep 100 -n 100 -b 2000 --exp_name exp3_hl1-6_ll1-32_k5 -rtg -k 5
```
Resuts:
Hopper-v1



TODO:
- some environments super-sensistive to k, why? bug?
- one assumption is that there is some consistency in the k timsteps. Probably doesn't work when complex physics (contact forces etc.) is involed - can we learn k?


