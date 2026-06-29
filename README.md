# Test Semantic Versioning

Flusso:

Push su main → workflow parte automaticamente

- @semantic-release/commit-analyzer legge i commit convenzionali (feat:, fix:, BREAKING CHANGE:) e decide se e quale versione rilasciare
- @semantic-release/changelog aggiorna CHANGELOG.md direttamente
- @semantic-release/exec aggiorna la versione in composer.json via jq
- @semantic-release/git committa entrambi i file su main con [skip ci] (per non triggerare il workflow di nuovo)
- @semantic-release/github crea il tag e la GitHub Release

| Prefisso commit      | Nuova Versione | Effetto sulla versione |
|--------------------- | -------------- | ---------------------- |
|                      | v1.0.0         |                        |
| nessuno dei previsti | v1.0.0         | Nessuno                |
| fix:                 | v1.0.**1**     | Incrementa Fix/Patch   |
| feat:                | v1.**1**.0     | Incrementa Minor       |
| BREAKING CHANGE:     | v**2**.0.0         | Incrementa Major       |

Look at automatic generated [Changelog file](CHANGELOG.md)

| Data e ora       | Note    |
| ---------------- | ------- |
| 2026-06-29 12:35 | Test 3.0 doc: |
