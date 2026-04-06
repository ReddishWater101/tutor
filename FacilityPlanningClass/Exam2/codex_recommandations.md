# Codex Recommendations

Only required changes are listed below. Recommendations are separated by lecture.

## Lecture 5 (L05): Personnel Requirements
- Replace `Compact spaces approx 75% of compact car %` with:
  `Compact spaces approx 0.75 x (compact-car fraction) x total spaces`
- Add one row-adjustment template so parking problems are actually executable:

```text
edge row: floor((W - y)/PW)
interior row: floor((W - y - 2x14)/PW)
ADA row: floor((W - y - ADAx12)/PW)
```

- Clarify food service order:
  `Peak eaters = on-site employees x fraction eating on-site`
  Then apply vending / serving line / full kitchen rules.
- Tighten the activity-based office bullet so it explicitly says it fits dynamic work with changing tools/settings.

## Lecture 6 (L06): Evaluating and Selecting Plans
- Rewrite the multi-criteria AHP section. The current `S` wording is misleading.
- Use this solve order:
  `For each criterion j: A^(j) -> normalize -> average rows -> s^(j)`
  `S = [s^(1) ... s^(m)]`
  `criteria matrix -> normalize -> average rows -> w`
  `v = S w`
- Fix typo: `A_comparion`.
- Add one interpretation rule:
  `a_jk > 1` means row item j is preferred to column item k.
  `a_jk < 1` means column item k is preferred.

## Lecture 7 (L07): Material Handling
- Relabel the returnable-container variables in plain English:
  `inside`, `outside`, `nested`, `trailer`, `Fit = number of containers that fit`.
- Add one storage-selection cue:
  `Choose storage based on protection needed, density needed, and accessibility/selectivity needed.`

## Lecture 8 (L08): Warehouse Operations and Layout
- Define `SS`, `OQ`, and `r/s` the first time they appear.
- Clarify the crossdock bullet so it also says when traditional storage is needed:
  `Traditional: receive -> store -> pick -> ship; use when buffering/storage is needed.`
- Add one receiving/storage adjacency tradeoff:
  `Receiving next to storage reduces put-away travel but can create congestion.`

## Lecture 9 (L09): ASRS
- Define `TP/D`, `T`, and `Q` in words.
- Replace or clarify `aisle_unit`; the width formula is incomplete without it.
- Add one sentence for Chebyshev travel:
  `Use max(th, tv), not th + tv, because horizontal and vertical travel occur simultaneously.`
