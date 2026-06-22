# Test Semantic Versioning

Flusso:

Push su main → workflow parte automaticamente
@semantic-release/commit-analyzer legge i commit convenzionali (feat:, fix:, BREAKING CHANGE:) e decide se e quale versione rilasciare
@semantic-release/changelog aggiorna CHANGELOG.md direttamente
@semantic-release/exec aggiorna la versione in composer.json via jq
@semantic-release/git committa entrambi i file su main con [skip ci] (per non triggerare il workflow di nuovo)
@semantic-release/github crea il tag e la GitHub Release

Look at automatic generated [Changelog file](CHANGELOG.md)

| Data e ora       | Note    |
| ---------------- | ------- |
| 2026-06-19 17:09 | Test 1  |
| 2026-06-19 17:36 | Test 2  |
| 2026-06-19 17:40 | Test 3  |
| 2026-06-19 17:52 | Test 4  |
| 2026-06-19 17:55 | Test 5  |
| 2026-06-19 17:57 | Test 6  |
| 2026-06-19 18:02 | Test 7  |
| 2026-06-22 11:37 | Test 2.0 |
| 2026-06-22 11:40 | Test 2.1 |
