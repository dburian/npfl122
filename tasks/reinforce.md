### Assignment: reinforce
#### Date: Deadline: Nov 21, 7:59 a.m.
#### Points: 4 points

Solve the continuous [CartPole-v1 environment](https://www.gymlibrary.dev/environments/classic_control/cart_pole/)
from the [Gym library](https://www.gymlibrary.dev/) using the REINFORCE
algorithm.

Your goal is to reach an average return of 490 during 100 evaluation episodes.

Start with the [reinforce.py](https://github.com/ufal/npfl122/tree/master/labs/06/reinforce.py)
template, which provides a simple network implementation in TensorFlow. Feel
free to use PyTorch ([reinforce.torch.py](https://github.com/ufal/npfl122/tree/master/labs/06/reinforce.torch.py))
or JAX instead, if you like.

During evaluation in ReCodEx, two different random seeds will be employed, and
you need to reach the required return on all of them. Time limit for each test
is 5 minutes.
