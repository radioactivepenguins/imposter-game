# Starting-player simulation

Executed November 2, 2026: **500,000 actual rounds**, **50,000 per mode/player-count combination**, using Node Web Crypto and the production `newRound` code. Both modes were tested at 3, 5, 8, 12, and 25 players. All 2,051 deterministic and statistical assertions passed.

## Why each player has the same probability

Let M = 2^32 and L = M − (M mod N). Draw an unsigned 32-bit integer. Discard values at or above L and draw again. For an accepted value, select `value % N`. Each player index has exactly L/N accepted integers, so each has probability 1/N when the source is uniform. This removes the incomplete final bucket instead of rounding a floating-point draw.

The starter draw occurs once before content and role assignment. It does not read history, Imposter positions, or card order; revealing cards never reruns it. Roles retain their existing independent weighted fairness rule. Starter probability remains uniform even when role probabilities are intentionally weighted by previous rounds.

## Observed distribution

| Players | Mode | Rounds | Expected per player | Observed min–max | Chi-square (N−1 degrees of freedom) |
| ---: | --- | ---: | ---: | ---: | ---: |
| 3 | classic | 50,000 | 33.333% | 33.136–33.460% | 0.90 |
| 3 | question | 50,000 | 33.333% | 33.172–33.546% | 1.11 |
| 5 | classic | 50,000 | 20.000% | 19.834–20.154% | 1.90 |
| 5 | question | 50,000 | 20.000% | 19.790–20.316% | 4.63 |
| 8 | classic | 50,000 | 12.500% | 12.282–12.710% | 8.73 |
| 8 | question | 50,000 | 12.500% | 12.284–12.954% | 15.72 |
| 12 | classic | 50,000 | 8.333% | 8.256–8.426% | 1.84 |
| 12 | question | 50,000 | 8.333% | 8.180–8.552% | 8.48 |
| 25 | classic | 50,000 | 4.000% | 3.752–4.222% | 39.93 |
| 25 | question | 50,000 | 4.000% | 3.852–4.208% | 23.58 |

Every player count was within the predefined six-standard-deviation sanity bound. The observed number of rounds where the starter was also an Imposter was likewise within six standard deviations of the expected proportion. Consecutive repeated starters occurred, as they should.

The statistics support the implementation but do not prove future frequencies or replace the integer-bucket argument. A short group session can have streaks. The code does not secretly rotate players, exclude the previous starter, or impose balancing quotas.

The deterministic tests also cover every starter position in both modes for every group size 3–25, the first and last full buckets, upper-bound rejection, invalid inputs, and independence from the content/role RNG. Exact per-player counts, joint starter/role tables, repeated-starter totals, and role-overlap counts are in `randomization-results.json`.

The runtime prefers browser Web Crypto. Its legacy Math.random fallback uses the same bucket rejection but cannot promise the statistical quality of Web Crypto. Neither source requires an external service.
