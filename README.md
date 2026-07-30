# `libre-ai-authz-biscuit`

Specialized Ed25519 Biscuit issuance, attenuation, verification, revocation and two-key rotation.

Security order is fixed: verify signature and key validity, derive the root authority block ID,
reject non-injective decoded terms, check revocation, require the canonical initial attenuation
block, inject authoritative request facts, then execute a bounded deny-by-default policy.
Tokens and private keys have redacted `Debug` implementations and are never returned in errors.

The browser boundary must never receive this crate's serialized tokens.

Security invariants and reviewer evidence are in [`SECURITY.md`](SECURITY.md),
[`G2-Z01-QUALIFICATION.md`](G2-Z01-QUALIFICATION.md) and [`evidence/`](evidence/).
The crate reuses the workspace-qualified exact `biscuit-auth` 5.0.0 registry
release with default features disabled and its matching internal parser grammar;
it carries no vendored or Git source.

## État du projet

<!-- libre-ai:project-status:begin -->
<!-- Section générée depuis project.v1.yaml — ne pas éditer à la main. -->

- Situation actuelle : Née verte en γ 3.4 ; six politiques datalog vendorées sous gate de dérive contre le pin contracts.
- Maturité : usable
- Exposition : spec-published
- Confiance : medium
- Preuves vérifiées le : 2026-07-30
- Avancement : 50 % du périmètre actuellement déclaré

<!-- libre-ai:project-status:end -->

La fiche [`project.v1.yaml`](./project.v1.yaml) est l'autorité de l'état du projet ; cette section en est générée et le gate de flotte échoue si elles divergent.
