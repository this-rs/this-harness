# this-harness

Runtime d'agent de `this-rs`, extrait du dépôt `this` en dépôt à part entière.
Contient le **cluster harnais** :

- `this-harness` (session, outils, ports)
- `this-agent` (preuve, énergie, nœud d'agent)
- `this-llm` (requête/réponse modèle)
- `this-llm-providers` (transports OpenAI-compatible/Anthropic)
- `this-module-lang` (le langage des programmes de module)
- `this-module-harness` (pont hôte)

Compilé **wasm + natif** ; consommé par les apps (atelier) et par `this` (via tag).

Voir `MOVE.md` pour la migration d'historique, et `docs/SPLIT-harness.md` (dans `this`)
pour la justification et le périmètre.
