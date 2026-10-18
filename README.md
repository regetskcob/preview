# preview

Testweise Auslieferung eines Branches von
[regetskcob.github.io](https://github.com/regetskcob/regetskcob.github.io) unter
https://www.regetskcob.de/preview/, ohne die Live-Seite anzufassen.

Dieses Repository enthält nur den Workflow. Er baut den gewählten Branch mit
`--environment preview` (im Blog `config/preview/hugo.toml`: ohne Umami, `noindex`,
ein Hinweis über dem Kopf, Links zeigen in die Vorschau) und veröffentlicht ihn als
Pages-Projektseite. Weil die Nutzerseite die Domain `www.regetskcob.de` trägt,
erscheint sie unter `/preview/`.

```sh
gh workflow run preview.yml --repo regetskcob/preview -f ref=horizont
```

Es gibt immer nur eine Vorschau; der nächste Lauf ersetzt sie.

Ohne `ref` wird die Vorschau geparkt: Jede Adresse unter `/preview/` leitet dann
auf dieselbe Seite der Live-Seite weiter (`/preview/galerie/` → `/galerie/`), mit
`noindex`. So bleibt der Weg für den nächsten Branch offen, ohne dass ein alter
Stand herumsteht.

```sh
gh workflow run preview.yml --repo regetskcob/preview
```
