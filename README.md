# Test Semantic Versioning

Flusso:

Push su main → workflow parte automaticamente

- @semantic-release/commit-analyzer legge i commit convenzionali (feat:, fix:, BREAKING CHANGE:) e decide se e quale versione rilasciare
- @semantic-release/changelog aggiorna CHANGELOG.md direttamente
- @semantic-release/exec aggiorna la versione in composer.json via jq
- @semantic-release/git committa entrambi i file su main con [skip ci] (per non triggerare il workflow di nuovo)
- @semantic-release/github crea il tag e la GitHub Release

Il messaggio deve iniziare con uno dei prefissi ammessi:

| Prefisso | Significato |
|----------|-------------|
| `feat:` | Nuova funzionalità |
| `fix:` | Correzione di un bug |
| `feat!:` | Nuova funzionalità con breaking change |
| `BREAKING CHANGE:` | Modifica incompatibile con versioni precedenti |
| `chore:` | Manutenzione, dipendenze, configurazione |
| `docs:` | Solo documentazione |
| `refactor:` | Ristrutturazione codice senza cambio di comportamento |

Formato: `<tipo>(<scope opzionale>): <descrizione>`

```
feat: aggiunta validazione IBAN nel form cliente
fix: corretto calcolo importo residuo con IVA inclusa
refactor(pratiche): estratto Service_RataService da MonitoringController
```

Se il messaggio non rispetta il formato, il commit viene bloccato con un messaggio di errore esplicativo.

Look at automatic generated [Changelog file](CHANGELOG.md)

| Data e ora       | Note    |
| ---------------- | ------- |
| 2026-06-29 12:35 | Test 3.0 doc: |
| 2026-06-29 16:05 | Test 3.1 feat!: |
