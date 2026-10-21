# CakeV4: selected rule bins

This folder contains the six general-purpose CakeV4 release files. Each file
has exactly the number of rule lines in its name. `CURRENT_RULES.csv` records
their byte sizes and SHA-256 hashes.

| File | Selection |
| --- | --- |
| `CakeV4.1K.rule` | 200-rule published CakeV3 core plus 800 independently ranked CakeV1 rules |
| `CakeV4.10K.rule` | 6,000-rule published CakeV3 core plus 4,000 independently ranked CakeV1 rules |
| `CakeV4.100K.rule` | Cross-wordlist maximin winner from the SkullSecurityComp portfolio |
| `CakeV4.1M.rule` | HashMob-medium nested 100K-basis portfolio |
| `CakeV4.5M.rule` | HashMob-medium 1M prefix plus retained 5M rules |
| `CakeV4.10M.rule` | HashMob-medium 5M prefix plus retained 10M rules |

The 1M, 5M, and 10M files are exact byte-prefix nested. The smaller bins are
independent selections.

## Independent selection

All 999,949 original CakeV1 rules were evaluated on balanced plaintext
targets derived from Collection1, Collection2, Collection3, and Antipublic.
Four randomized rule orders assigned each recovered password to its earliest
covering rule; mean marginal credit estimates each rule's Shapley value in the
coverage game. RockYou, benchmark target hashes, and passwords recovered from
the benchmark were not used for ranking.

For the public 1K and 10K files, retained-core proportions were swept in 10%
steps. A candidate first had to beat or tie published CakeV3 on Aptoide,
HIBP, hashes.org, and DailyQuiz with Skull, medium, and large word samples.
Among eligible candidates, selection maximized the worst normalized
Collection4+5 score across the three wordlist families; geometric mean broke
ties. The 100K choice used the same maximin objective across the three current
CakeV4 portfolios and the published CakeV3 Transfer file.

## Direct comparison with published CakeV3

Independent Collection4+5 totals show that each selected small bin beats its
published CakeV3 counterpart on every wordlist family:

| Bin | Ruleset | Skull words | Medium words | Large words |
| --- | --- | ---: | ---: | ---: |
| 1K | CakeV4 | 6,067 | 7,157 | 5,737 |
| 1K | CakeV3 | 3,273 | 4,161 | 2,823 |
| 10K | CakeV4 | 12,682 | 14,664 | 12,247 |
| 10K | CakeV3 | 9,490 | 11,417 | 8,528 |
| 100K | CakeV4 | 20,848 | 23,019 | 20,835 |
| 100K | CakeV3 Transfer | 18,564 | 20,676 | 18,209 |

Held-out net gains over the same published CakeV3 files were:

| Bin / word family | Aptoide | HIBP | hashes.org | DailyQuiz |
| --- | ---: | ---: | ---: | ---: |
| 1K / Skull | +108 | +1 | +14 | +787 |
| 1K / medium | +64 | 0 | +5 | +806 |
| 1K / large | +136 | +3 | +15 | +750 |
| 10K / Skull | +185 | +21 | +48 | +1,499 |
| 10K / medium | +117 | +9 | +18 | +1,224 |
| 10K / large | +239 | +17 | +38 | +1,491 |
| 100K / Skull | +29 | +107 | +199 | +1,535 |
| 100K / medium | +50 | +85 | +165 | +1,115 |
| 100K / large | +105 | +129 | +157 | +1,670 |

The selected medium 1M basis improved its preceding CakeV4 file by **+3,081
Aptoide, +1,195 HIBP, +1,461 hashes.org, +1,391 DailyQuiz**, and **+432** on
an evenly spaced 100,000-word native sample. Propagating that basis produced
positive fixed-word results at both larger bins:

| Bin | Aptoide | Collection4 | Collection5 | HIBP | hashes.org | DailyQuiz |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| 5M | +117 | +259 | +240 | +15 | +22 | +1,268 |
| 10M | +120 | +236 | +224 | +18 | +27 | +1,196 |

These measurements compare exact hit sets under identical inputs. The original
full Wordlist Tests sheet and the teammates' closed benchmark have not been
rerun with CakeV4, so their exact scores and ranks remain unknown. The results
above establish improvement on the stated independent and held-out tests; they
do not claim universal dominance on undisclosed data.

The rule files use Git LFS. Run `git lfs pull` after cloning if Git displays
pointer files.
