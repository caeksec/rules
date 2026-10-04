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

The three `buka_400k` entries above all refer to the **HashMob-medium** wordlist. Buka is the highest-scoring non-Cake row at or below each of those size caps in that section, but its 399,986 rules are not size-matched to 5M or 10M. That section has no non-Cake 5M or 10M entries. Its closest 1M-size rival is `Robot_CurrentBestRules` (942,680 rules; 3,492,910 cracked), which trails the CakeV3.1M lower bound by at least 124,068.

The same sheet has closer deep-bin rivals on its other wordlists:

| Sheet wordlist | Bin | CakeV3 cracked | Strongest non-Cake rule at or below cap (rules) | Rival cracked | CakeV3 lead |
| --- | --- | ---: | --- | ---: | ---: |
| SkullSecurityComp | 1M | 3,590,634 | `sapphire_v3.minimized` (742,903) | 3,276,029 | +314,605 |
| SkullSecurityComp | 5M | 3,640,987 | `Vavaldi.5M` (4,998,394) | 3,408,780 | +232,207 |
| SkullSecurityComp | 10M | 3,661,504 | `Vavaldi.10M` (9,996,621) | 3,546,615 | +114,889 |
| HashMob large | 1M | ≥4,105,202 | `buka_400k` (399,986) | 3,858,156 | ≥247,046 |
| HashMob large | 5M | ≥4,161,658 | `Vavaldi.5M` (4,998,394) | 4,026,858 | ≥134,800 |
| HashMob large | 10M | ≥4,161,658 | `Vavaldi.10M` (9,996,621) | 4,114,684 | ≥46,974 |

## Transfer checks

On six non-HIBP HashMob found-hash samples (Dogzer, Raaga, Armeec, Atspace, Newlook, Chordie), these exact six files won 30 same-input comparisons, tied six on Newlook, and lost none against the selected local HashMob, Fordy, and Vavaldi comparator files. The comparator within each bin used the same target, word sample, hash mode, and rule count. The samples contain previously recovered hashes; tests on current left files tied at zero and did not rank rule quality. This is evidence of transfer to the tested samples, not a guarantee against other private rulesets or unseen lists.

The small-bin selection also used separate DailyQuiz MD5, hashes.org-derived SHA-1, and HIBP SHA-1 checks. The 100K blend won most of the independent 13-dataset HIBP holdout comparisons against other tested CakeV3 100K mixes. The selected deep files led the other original CakeV3 suites on the HIBP V8 SHA-1 sample with each of the three wordlists.

The files use Git LFS. Run `git lfs pull` after cloning if Git displays pointer files.
