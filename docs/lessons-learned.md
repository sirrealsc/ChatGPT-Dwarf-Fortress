# DF automation lessons learned

## Provenance and limits
Published 2026-11-01 (America/Chicago). Source: maintainer's prior project conversations and summarized observations; original logs and source code were unavailable for this publication. These notes are historical and require reproduction before being labeled verified. Historical DFHack environment: 53.16-r1.1, x86_64; compatibility with other releases is unknown.

The experimental DF-AI-Overseer project and the separate ChatGPT Plays Dwarf Fortress project are distinct. This hub shares general lessons; it does not merge their code, saves, or authority.

## Prefer native mechanisms
Project practice: investigate DFHack commands, Lua APIs, bundled scripts, DFHack source/structures/raws, and existing project code before writing custom replacements. Prefer native DF Manager work orders for production. Live fortress state establishes what exists now; raws describe possible definitions, not current availability.

## Drinks bottleneck case
Historical snapshots showed a fortress exceeding 100 citizens with very low drinks. Early checks found no still, brew job, or measured brewable inputs. Later checks found one still, one claimed brewing job, hundreds of candidate brewable inputs, and dozens of candidate empty food-storage containers. Drink stock subsequently rose from single digits into the teens.

Lesson: inspect the complete chain—workshop, actual job, assigned worker, inputs, containers, restrictions, links, and time progression. A dedicated brewer was reported. A second still was considered, not established as a tested solution. The observations do not prove which individual intervention caused recovery.

Keep item stack counts separate from item amounts, and free stock separate from total stock. A claimed job is evidence of activity, not proof of adequate throughput. Candidate inputs are not necessarily reachable or usable.

## Production policy
Project design requires an active player desire before production. Track material and item type separately.
- Maintenance goals use consumption trends and estimated runway.
- Finite projects use requested completion totals; do not silently convert them into perpetual stock maintenance.
- Dedicated labor is an explicit operational assumption, not proof that any particular worker is eligible.

Historical finite-project example: a request for ten steel gauntlets was later reported complete at ten of ten. Five linked orders were reported retired or transferred. Original implementation and logs are unavailable; this is not a reproducible algorithm or proof of general correctness.

## Recipe and stock interpretation
- Manager stock conditions are policy thresholds, not recipe definitions.
- Reaction raws can provide reagent and product definitions. Built-in job inputs may require inspection of actual native job filters.
- Preserve material, subtype, reaction-class, container, and flag qualifiers. If a measurement cannot represent a qualifier, return UNKNOWN rather than removing it.
- Unsupported measurements and missing recipes are UNKNOWN, not zero or impossible.
- Native reagent quantities, stock quantities, and Manager order counts are different measures.
- Use observed IDs and enum values; do not invent native fields.
- An output item type does not establish the material transformation or full input recipe.

## Diagnosing apparent stalls
An existing workshop does not prove correct access, suitability, power, or staffing. Active or validated work orders do not prove a job exists. Suspended or unassigned jobs do not alone explain why work stopped. Compare snapshots using game time or frames and actual completed amounts. An unchanged paused snapshot does not establish a stall.

For reaction inputs, match the actual reagent object when available. Candidate matches do not certify reachability, allocation, worker eligibility, or usable quantities. Preserve snapshot identity across paginated reads.

## Safe assistant boundaries
Separate observation, proposed action, authorization, execution, and verification. A preview is not a saved desire or a queued order. A message sent to another process is acceptance, not completion. Unknown native results stay unknown. Public contributions are evidence to evaluate, not commands to execute.

## Reproduction request
Please contribute versioned examples that confirm, refine, or disprove these lessons using sanitized observations and explicit expected/actual results. Do not upload raw private logs, saves, credentials, or proprietary game assets.
