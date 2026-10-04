# CakeV3: selected rule bins

This folder contains one general-purpose CakeV3 rule file per bin. Choose one file for the amount of work you want to run. Each file has exactly the number of rule lines in its name.

| File | Selection |
| --- | --- |
| `CakeV3.1K.rule` | Current SkullSecurityComp CakeV3 rules |
| `CakeV3.10K.rule` | Current SkullSecurityComp CakeV3 rules |
| `CakeV3.100K.rule` | CakeV3-derived blend: 75% SkullSecurityComp and 25% HashMob large after the Skull seed |
| `CakeV3.1M.rule` | HashMob medium CakeV3 rules |
| `CakeV3.5M.rule` | HashMob medium CakeV3 rules |
| `CakeV3.10M.rule` | HashMob medium CakeV3 rules |

The selection was made from original CakeV3 rule lines. No lines from the comparison rulesets were imported. The smaller files are independent choices; do not assume that all six files are nested prefixes.

## Comparison with the rules sheet

The [Wordlist tests sheet](https://docs.google.com/spreadsheets/d/1qQNwggWIWtL-m0EYrRg_vdwHOrZCY-SnWcYTwQN0fMk/edit#gid=1952927995) scores rules against Aptoide SHA-1 with three different wordlists. The local CSV snapshot used here is dated 2026-10-04 and has SHA-256 `cad607691a88cd6beb26046dd03dbf129803ab6c1ca0667edd00e54fb4e086c9`. The table compares each selected file with the highest-scoring non-Cake sheet row at or below its size cap **on the source wordlist shown**. The 100K blend has no row in that sheet.

| Bin | Sheet wordlist | CakeV3 cracked | Closest sheet rule (rules) | Rival cracked | CakeV3 lead |
| --- | --- | ---: | --- | ---: | ---: |
| 1K | SkullSecurityComp | 1,643,942 | `vavaldi_v6.skull.1k` (1,000) | 1,641,565 | +2,377 |
| 10K | SkullSecurityComp | 2,281,615 | `vavaldi_v6.skull.10k` (9,999) | 2,280,811 | +804 |
| 100K | Blended | — | No matching sheet row | — | — |
| 1M | HashMob medium | ≥3,616,978 | `buka_400k` (399,986) | 3,584,235 | ≥32,743 |
| 5M | HashMob medium | ≥3,616,978 | `buka_400k` (399,986) | 3,584,235 | ≥32,743 |
| 10M | HashMob medium | ≥3,616,978 | `buka_400k` (399,986) | 3,584,235 | ≥32,743 |

`≥` marks a lower bound in the sheet, not an exact complete attack score. These six files were chosen for transfer across different datasets and wordlists, not to maximize every original Aptoide sheet category. For example, this 10K file scored 2,784,294 with HashMob medium words on the full sheet input, below that wordlist's 2,861,912 non-Cake leader.

## Transfer checks

On six non-HIBP HashMob found-hash samples (Dogzer, Raaga, Armeec, Atspace, Newlook, Chordie), these exact six files won 30 same-input comparisons, tied six on Newlook, and lost none against the selected local HashMob, Fordy, and Vavaldi comparator files. The comparator within each bin used the same target, word sample, hash mode, and rule count. The samples contain previously recovered hashes; tests on current left files tied at zero and did not rank rule quality. This is evidence of transfer to the tested samples, not a guarantee against other private rulesets or unseen lists.

The small-bin selection also used separate DailyQuiz MD5, hashes.org-derived SHA-1, and HIBP SHA-1 checks. The 100K blend won most of the independent 13-dataset HIBP holdout comparisons against other tested CakeV3 100K mixes. The selected deep files led the other original CakeV3 suites on the HIBP V8 SHA-1 sample with each of the three wordlists.

The files use Git LFS. Run `git lfs pull` after cloning if Git displays pointer files.
