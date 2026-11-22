# coalfire-vdr-tap

FedRAMP's Consolidated Rules for 2026 ask a provider to rate the Potential Agency Impact (PAIN, N1 to N5) of every detected vulnerability, and do not prescribe how to get from a vulnerability on an asset to a rating. Coalfire has published a methodology that does: [*Coalfire's stance on Potential Agency Impact (PAIN) ratings*](https://cdn.coalfire.com/prod/resources/Whitepapers/White-Paper-Coalfire-PAIN-Rating_2026-9-30.pdf) (September 2026). This plugin implements that method on [TAP](https://github.com/unified-systems-com/tap), using data from the grid.

The method crosses an asset's criticality with the CVSS Environmental severity of the finding on that asset to get a customer effect, combines the effect with agency scope to get the N-rating, and holds a finding at N3 while either input is missing.

This plugin holds **only what is Coalfire's own**: the criticality classification and the calibration that uses it. Everything that is true of the environment under evaluation whichever method rates it (which asset a finding belongs to, internet reachability, likely exploitability, an asset's CVSS Environmental metrics, agency scope, the PAIN levels and the remediation timeframes) lives in [`fedramp_20x_vdr`](https://github.com/unified-systems-com/fedramp-20x-vdr-tap), so that several methods can rate the same environment side by side from the same inputs.

## Status

Specification in progress. There is no code in this repository yet; the spec arrives first, as `specs/spec-coalfire-vdr-v0.md`.

The method is Coalfire's; any error in this implementation is ours. This is not a statement of FedRAMP compliance.

This plugin is developed with AI coding assistance (Claude Code) under the direction of the maintainer.
