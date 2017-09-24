Notes on the different kinds of experiments on models are written here.

# Attempt 0: Using call site and original function size as RL states

- There are several call sites throghout a program. It definitely makes
  sense to think of a way to weight all these call sites differently, but
  that is too much additional work. In this version, I will just use the
  standard RL discount factor.
- Hypothesis: Works well to optimize a single compilation unit, but will not
  generalize to arbitary files (or it will simply take too long).
