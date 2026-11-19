# Migration depuis `this` (avec historique)

Depuis un clone de `this` (une session stable, arbre propre) :

```bash
git clone <this> tmp && cd tmp
git filter-repo \
  --path crates/this-harness --path crates/this-agent \
  --path crates/this-llm --path crates/this-llm-providers \
  --path crates/this-module-lang --path crates/this-module-harness \
  --path-rename crates/:
# puis copier dans this-harness/crates, corriger les Cargo.toml (deps internes),
# initialiser le workspace, tagger v0.0.1, et basculer this/atelier sur le tag.
```

Sans `git-filter-repo` : `cp -r` (on perd l'historique, plus simple).

Après déplacement :
- `this` : remplacer `path = "../this/crates/this-harness"` → `this-harness = { git = "<remote>", tag = "v0.0.1" }`.
- `atelier` : idem.
- Ce repo : `cargo test --workspace` (wasm + natif) + `cargo clippy -- -D warnings`.
