### Assignment: q_learning
#### Date: Deadline: Oct 31, 7:59 a.m.
#### Points: 4 points

Solve the [MountainCar-v0 environment](https://www.gymlibrary.dev/environments/classic_control/mountain_car/)
from the [Gym library](https://www.gymlibrary.dev/) using the Q-learning
reinforcement learning algorithm. Note that this task does not require
TensorFlow.

The environment methods and properties are described in the `monte_carlo` assignment.
Once you finish training (which you indicate by passing `start_evaluation=True`
to `reset`), your goal is to reach an average return of -150 during 100
evaluation episodes.

You can start with the [q_learning.py](https://github.com/ufal/npfl122/tree/master/labs/03/q_learning.py)
template, which parses several useful parameters, creates the environment
and illustrates the overall usage. Note that setting hyperparameters of
Q-learning is a bit tricky – I usually start with a larger value of $ε$ (like 0.2
or even 0.5) and then gradually decrease it to almost zero.

During evaluation in ReCodEx, three different random seeds will be employed, and
you need to reach the required return on all of them. The time limit for each
test is 5 minutes.
