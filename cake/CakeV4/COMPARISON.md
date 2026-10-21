# CakeV4: selected rule bins

This folder contains the six general-purpose CakeV4 release files. Each file
has exactly the number of rule lines in its name. `CURRENT_RULES.csv` records
their byte sizes and SHA-256 hashes.

| File | Selection |
| --- | --- |
| `CakeV4.1K.rule` | Full-wordlist-validated SkullSecurityComp CakeV4 |
| `CakeV4.10K.rule` | Full-wordlist-validated SkullSecurityComp CakeV4 |
| `CakeV4.100K.rule` | Full-wordlist-validated SkullSecurityComp CakeV4 |
| `CakeV4.1M.rule` | Full-wordlist-validated HashMob-medium semantic-alias suite |
| `CakeV4.5M.rule` | HashMob-medium 1M set plus safe alias replacements |
| `CakeV4.10M.rule` | Exact 5M byte prefix plus safe alias replacements |

The 1M rule set is contained in 5M, and 5M is an exact byte prefix of 10M.
The smaller bins are independent selections.

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

## Proven medium deep chain

The selected 1M file exhausted the complete HashMob-medium/Aptoide attack at
**3,693,530**, a gain of **+593** over the freshly rerun CakeV3 1M score of
3,692,937. Its 255 outgoing rules have equivalent retained forms: 239 `D0`
versus `[` aliases and 16 commuting-substitution pairs. Hashcat produced
byte-identical output for each pair on the edge-case probe set, so the 255
independently ranked additions cannot remove coverage.

The 5M and 10M suites contain every selected 1M rule. They replace 37,680 and
39,609 redundant spellings with rules already selected by the other CakeV4
wordlist suites. The removed compact/spaced command pairs produced identical
Hashcat output on the probe set, and 5M is an exact byte prefix of 10M. Before
these additional safe replacements, exact hit-set subtraction proved gains
of at least **+38** over CakeV3 at both bins. Complete absolute sheet attacks
for the final 5M and 10M files have not been rerun.

A broader sample-trained deep portfolio won the fixed-word validation gates,
but its long rules reduced full-attack throughput from the predecessor's
measured 128-second 1M pass to an estimated 18 hours. It was rejected for the
everyday release before completion.

The teammates' closed benchmark also remains unavailable. Its exact CakeV4
scores and ranks cannot be claimed until they run these hashes. The rule files
use Git LFS; run `git lfs pull` after cloning if Git displays pointer files.
