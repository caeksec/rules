# CakeV4: selected rule bins

This folder contains the six general-purpose CakeV4 release files. Each file
has exactly the number of rule lines in its name. `CURRENT_RULES.csv` records
their byte sizes and SHA-256 hashes.

| File | Selection |
| --- | --- |
| `CakeV4.1K.rule` | Full-wordlist-validated SkullSecurityComp CakeV4 |
| `CakeV4.10K.rule` | Full-wordlist-validated SkullSecurityComp CakeV4 |
| `CakeV4.100K.rule` | Full-wordlist-validated SkullSecurityComp CakeV4 |
| `CakeV4.1M.rule` | HashMob-medium nested 100K-basis portfolio |
| `CakeV4.5M.rule` | HashMob-medium 1M prefix plus retained 5M rules |
| `CakeV4.10M.rule` | HashMob-medium 5M prefix plus retained 10M rules |

The 1M, 5M, and 10M files are exact byte-prefix nested. The smaller bins are
independent selections.

## Independent generation

The selected small files replace one CakeV3 transformation,
`[[[[[^d^i^o^t^p^A`, with `]]dl`, a transformation discovered in CakeV1.
The addition and removal were chosen from public HashMob, HashMob frequency
tail, and Collection plaintext coverage. RockYou, benchmark target hashes,
and passwords recovered from the benchmark were not used for ranking.

Broader CakeV1 Shapley portfolios were also trained on Collection1–3 and
Antipublic and passed 10,000-word and stratified validation. The proposed 1K
release then scored only **1,367,705** on the complete Skull wordlist and
**1,988,912** on the complete HashMob-medium wordlist. Those candidates were
rejected. The release keeps the smaller independently chosen swap that had
already passed the complete benchmark. This full-wordlist veto prevents the
sample-to-full failure from entering CakeV4.

## Full Aptoide comparison

All rows below use the same 5,198,342-hash Aptoide SHA-1 left list and the
complete SkullSecurityComp wordlist. The closest sheet rival uses 90–100% of
CakeV4's rule count and has the most cracks in that range.

| Bin | CakeV3 | CakeV4 | Gain over CakeV3 | Closest sheet rival | Rival score | CakeV4 lead |
| --- | ---: | ---: | ---: | --- | ---: | ---: |
| 1K | 1,643,942 | **1,645,363** | +1,421 | `vavaldi_v6.skull.1k` | 1,641,565 | +3,798 |
| 10K | 2,281,615 | **2,282,662** | +1,047 | `vavaldi_v6.skull.10k` | 2,280,811 | +1,851 |
| 100K | 2,967,748 | **2,968,181** | +433 | `HashMob.100k` | 2,748,401 | +219,780 |

The same-input transfer checks for the one-rule portfolio also improved or
tied every measured holdout:

| Bin | DailyQuiz gain | hashes.org gain | HIBP gain |
| --- | ---: | ---: | ---: |
| 1K | +789 | +16 | +53 |
| 10K | +426 | +2 | +17 |
| 100K | +65 | 0 | 0 |

## Nested medium chain

The selected medium 1M basis improved its preceding CakeV4 file by **+3,081
Aptoide, +1,195 HIBP, +1,461 hashes.org, +1,391 DailyQuiz**, and **+432** on
an evenly spaced 100,000-word native sample. Propagating that basis produced
positive fixed-word results at both larger bins:

| Bin | Aptoide | Collection4 | Collection5 | HIBP | hashes.org | DailyQuiz |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| 5M | +117 | +259 | +240 | +15 | +22 | +1,268 |
| 10M | +120 | +236 | +224 | +18 | +27 | +1,196 |

The preceding medium CakeV4 files had exact relative gains of +41 at 1M and
+38 at both 5M and 10M over their corresponding CakeV3 files. The nested
files above improved again on every measured target. Their complete original
sheet attacks have not been rerun, so this document does not invent absolute
full-wordlist scores for those three bins.

The teammates' closed benchmark also remains unavailable. Its exact CakeV4
scores and ranks cannot be claimed until they run these hashes. The rule files
use Git LFS; run `git lfs pull` after cloning if Git displays pointer files.
