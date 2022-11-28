### Assignment: trace_algorithms
#### Date: Deadline: Dec 12, 7:59 a.m.
#### Points: 4 points
#### Examples: trace_algorithms_examples
#### Tests: trace_algorithms_tests

Starting with the [trace_algorithms.py](https://github.com/ufal/npfl122/tree/master/labs/09/trace_algorithms.py)
template, implement the following state value estimations:
- use $n$-step estimates for a given $n$;
- if requested, use eligibility traces with a given $λ$;
- allow off-policy correction using importance sampling with control variates,
  optionally clipping the individual importance sampling ratios by a given
  threshold.

#### Examples Start: trace_algorithms_examples
_Note that your results may be slightly different, depending on your CPU type and whether you use a GPU._
- `python3 trace_algorithms.py --n=1`
```
Episode 100, mean 100-episode return -96.50 +-92.02
Episode 200, mean 100-episode return -53.64 +-76.70
Episode 300, mean 100-episode return -29.03 +-54.84
Episode 400, mean 100-episode return -8.78 +-21.69
Episode 500, mean 100-episode return -14.24 +-41.76
Episode 600, mean 100-episode return -4.57 +-17.56
Episode 700, mean 100-episode return -7.90 +-27.92
Episode 800, mean 100-episode return -2.17 +-16.67
Episode 900, mean 100-episode return -2.07 +-14.01
Episode 1000, mean 100-episode return 0.13 +-13.93
The mean 1000-episode return after evaluation -35.05 +-84.82
```
- `python3 trace_algorithms.py --n=4`
```
Episode 100, mean 100-episode return -74.01 +-89.62
Episode 200, mean 100-episode return -4.84 +-20.95
Episode 300, mean 100-episode return 0.37 +-11.81
Episode 400, mean 100-episode return 1.82 +-8.04
Episode 500, mean 100-episode return 1.28 +-8.66
Episode 600, mean 100-episode return 3.13 +-7.02
Episode 700, mean 100-episode return 0.76 +-8.05
Episode 800, mean 100-episode return 2.05 +-8.11
Episode 900, mean 100-episode return 0.98 +-9.22
Episode 1000, mean 100-episode return 0.29 +-9.13
The mean 1000-episode return after evaluation -11.49 +-60.05
```
- `python3 trace_algorithms.py --n=8`
```
Episode 100, mean 100-episode return -92.61 +-105.75
Episode 200, mean 100-episode return -6.49 +-21.66
Episode 300, mean 100-episode return -0.05 +-11.13
Episode 400, mean 100-episode return 1.40 +-7.92
Episode 500, mean 100-episode return -0.79 +-13.78
Episode 600, mean 100-episode return -3.73 +-25.97
Episode 700, mean 100-episode return 1.13 +-13.67
Episode 800, mean 100-episode return -5.98 +-28.62
Episode 900, mean 100-episode return 0.79 +-9.62
Episode 1000, mean 100-episode return 2.09 +-7.78
The mean 1000-episode return after evaluation -55.86 +-96.41
```
- `python3 trace_algorithms.py --n=4 --trace_lambda=0.6`
```
Episode 100, mean 100-episode return -85.33 +-91.17
Episode 200, mean 100-episode return -16.06 +-39.97
Episode 300, mean 100-episode return -2.74 +-15.78
Episode 400, mean 100-episode return -0.33 +-9.93
Episode 500, mean 100-episode return 1.39 +-9.48
Episode 600, mean 100-episode return 1.59 +-9.26
Episode 700, mean 100-episode return 3.66 +-6.99
Episode 800, mean 100-episode return 2.08 +-7.26
Episode 900, mean 100-episode return 1.32 +-8.76
Episode 1000, mean 100-episode return 3.33 +-7.27
The mean 1000-episode return after evaluation 7.93 +-2.63
```
- `python3 trace_algorithms.py --n=8 --trace_lambda=0.6`
```
Episode 100, mean 100-episode return -117.72 +-113.58
Episode 200, mean 100-episode return -24.27 +-57.52
Episode 300, mean 100-episode return -6.54 +-27.78
Episode 400, mean 100-episode return 0.11 +-9.50
Episode 500, mean 100-episode return 3.17 +-7.27
Episode 600, mean 100-episode return 1.99 +-8.11
Episode 700, mean 100-episode return 0.89 +-8.25
Episode 800, mean 100-episode return 3.24 +-8.59
Episode 900, mean 100-episode return 3.04 +-6.91
Episode 1000, mean 100-episode return 1.26 +-8.61
The mean 1000-episode return after evaluation -7.84 +-55.17
```
- `python3 trace_algorithms.py --n=1 --off_policy`
```
Episode 100, mean 100-episode return -68.47 +-73.52
Episode 200, mean 100-episode return -29.11 +-34.15
Episode 300, mean 100-episode return -20.30 +-31.24
Episode 400, mean 100-episode return -13.44 +-25.04
Episode 500, mean 100-episode return -4.72 +-13.75
Episode 600, mean 100-episode return -3.07 +-17.63
Episode 700, mean 100-episode return -2.70 +-13.81
Episode 800, mean 100-episode return 1.32 +-11.79
Episode 900, mean 100-episode return 0.78 +-8.95
Episode 1000, mean 100-episode return 1.15 +-9.27
The mean 1000-episode return after evaluation -12.63 +-62.51
```
- `python3 trace_algorithms.py --n=4 --off_policy`
```
Episode 100, mean 100-episode return -96.25 +-105.93
Episode 200, mean 100-episode return -26.21 +-74.65
Episode 300, mean 100-episode return -4.84 +-31.78
Episode 400, mean 100-episode return -0.34 +-9.46
Episode 500, mean 100-episode return 1.15 +-8.49
Episode 600, mean 100-episode return 2.95 +-7.20
Episode 700, mean 100-episode return 0.94 +-10.19
Episode 800, mean 100-episode return 0.13 +-9.27
Episode 900, mean 100-episode return 1.95 +-9.69
Episode 1000, mean 100-episode return 1.91 +-7.59
The mean 1000-episode return after evaluation 6.79 +-3.68
```
- `python3 trace_algorithms.py --n=8 --off_policy`
```
Episode 100, mean 100-episode return -180.08 +-112.11
Episode 200, mean 100-episode return -125.56 +-124.82
Episode 300, mean 100-episode return -113.66 +-125.12
Episode 400, mean 100-episode return -77.98 +-117.08
Episode 500, mean 100-episode return -23.71 +-69.71
Episode 600, mean 100-episode return -21.44 +-67.38
Episode 700, mean 100-episode return -2.43 +-16.31
Episode 800, mean 100-episode return 2.38 +-7.42
Episode 900, mean 100-episode return 1.29 +-7.78
Episode 1000, mean 100-episode return 0.84 +-8.37
The mean 1000-episode return after evaluation 7.03 +-2.37
```
- `python3 trace_algorithms.py --n=1 --off_policy --vtrace_clip=1`
```
Episode 100, mean 100-episode return -71.85 +-75.59
Episode 200, mean 100-episode return -29.60 +-39.91
Episode 300, mean 100-episode return -23.11 +-33.97
Episode 400, mean 100-episode return -12.00 +-21.72
Episode 500, mean 100-episode return -5.93 +-15.92
Episode 600, mean 100-episode return -7.69 +-16.03
Episode 700, mean 100-episode return -2.95 +-13.75
Episode 800, mean 100-episode return 0.45 +-9.76
Episode 900, mean 100-episode return 0.65 +-9.36
Episode 1000, mean 100-episode return -1.56 +-11.53
The mean 1000-episode return after evaluation -24.25 +-75.88
```
- `python3 trace_algorithms.py --n=4 --off_policy --vtrace_clip=1`
```
Episode 100, mean 100-episode return -76.39 +-83.74
Episode 200, mean 100-episode return -3.32 +-13.97
Episode 300, mean 100-episode return -0.33 +-9.49
Episode 400, mean 100-episode return 2.20 +-7.80
Episode 500, mean 100-episode return 1.49 +-7.72
Episode 600, mean 100-episode return 2.27 +-8.67
Episode 700, mean 100-episode return 1.07 +-9.07
Episode 800, mean 100-episode return 3.17 +-6.27
Episode 900, mean 100-episode return 3.25 +-7.39
Episode 1000, mean 100-episode return 0.70 +-8.61
The mean 1000-episode return after evaluation 7.70 +-2.52
```
- `python3 trace_algorithms.py --n=8 --off_policy --vtrace_clip=1`
```
Episode 100, mean 100-episode return -110.07 +-106.29
Episode 200, mean 100-episode return -7.22 +-32.31
Episode 300, mean 100-episode return 0.54 +-9.65
Episode 400, mean 100-episode return 2.03 +-7.82
Episode 500, mean 100-episode return 1.64 +-8.63
Episode 600, mean 100-episode return 1.54 +-7.28
Episode 700, mean 100-episode return 2.80 +-7.86
Episode 800, mean 100-episode return 1.69 +-7.26
Episode 900, mean 100-episode return 1.17 +-8.59
Episode 1000, mean 100-episode return 2.39 +-7.59
The mean 1000-episode return after evaluation 7.57 +-2.35
```
#### Examples End:
#### Tests Start: trace_algorithms_tests
_Note that your results may be slightly different, depending on your CPU type and whether you use a GPU._
- `python3 trace_algorithms.py --episodes=50 --n=1`
```
The mean 1000-episode return after evaluation -196.80 +-25.96
```
- `python3 trace_algorithms.py --episodes=50 --n=4`
```
The mean 1000-episode return after evaluation -165.45 +-78.01
```
- `python3 trace_algorithms.py --episodes=50 --n=8`
```
The mean 1000-episode return after evaluation -144.47 +-92.73
```
- `python3 trace_algorithms.py --episodes=50 --n=4 --trace_lambda=0.6`
```
The mean 1000-episode return after evaluation -170.70 +-72.93
```
- `python3 trace_algorithms.py --episodes=50 --n=8 --trace_lambda=0.6`
```
The mean 1000-episode return after evaluation -155.04 +-86.17
```
- `python3 trace_algorithms.py --episodes=50 --n=1 --off_policy`
```
The mean 1000-episode return after evaluation -189.16 +-46.74
```
- `python3 trace_algorithms.py --episodes=50 --n=4 --off_policy`
```
The mean 1000-episode return after evaluation -159.09 +-83.40
```
- `python3 trace_algorithms.py --episodes=50 --n=8 --off_policy`
```
The mean 1000-episode return after evaluation -166.82 +-76.04
```
- `python3 trace_algorithms.py --episodes=50 --n=1 --off_policy --vtrace_clip=1`
```
The mean 1000-episode return after evaluation -198.50 +-17.93
```
- `python3 trace_algorithms.py --episodes=50 --n=4 --off_policy --vtrace_clip=1`
```
The mean 1000-episode return after evaluation -144.76 +-92.48
```
- `python3 trace_algorithms.py --episodes=50 --n=8 --off_policy --vtrace_clip=1`
```
The mean 1000-episode return after evaluation -167.63 +-75.87
```
#### Tests End:
