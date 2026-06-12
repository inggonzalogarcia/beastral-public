# Términos y Condiciones — BeAstral

Documentos legales versionados, servidos por **GitHub Pages** desde este folder. El bot Telegram [@BeAstralBot](https://t.me/BeAstralBot) linkea a estas URLs cuando solicita aceptación al usuario.

## Estructura

```
docs/terms/
  v1/
    es.md  en.md  pt.md  it.md  fr.md  de.md
  v2/   ← futuro: nueva versión, mismo set de idiomas
```

## Convención de versionado

- Versión vigente: definida por la env var `TERMS_VERSION` del backend (webapp-api del stack privado).
- Cuando se bumpea (v1 → v2), se crea `v2/` con los 6 documentos y se actualiza la env var. A partir de ese momento, todos los usuarios con `terms_version != v2` reciben el T&C nuevo al próximo interactuar (gate automático).
- **Los folders viejos NO se borran** — quedan accesibles por path inmutable, permitiendo al usuario consultar exactamente la versión que aceptó.

## URLs públicas (GitHub Pages)

Una vez habilitado Pages (Settings → Pages → Source: `main` branch, folder `/docs`), los documentos quedan disponibles en:

```
https://inggonzalogarcia.github.io/beastral-public/terms/v1/es
https://inggonzalogarcia.github.io/beastral-public/terms/v1/en
https://inggonzalogarcia.github.io/beastral-public/terms/v1/pt
https://inggonzalogarcia.github.io/beastral-public/terms/v1/it
https://inggonzalogarcia.github.io/beastral-public/terms/v1/fr
https://inggonzalogarcia.github.io/beastral-public/terms/v1/de
```

> Para habilitar: GitHub repo → Settings → Pages → Build and deployment → Source: "Deploy from a branch" → Branch: `main` / `/docs` → Save.

## Trazabilidad legal

Cada aceptación queda registrada en el backend con `terms_version` + `terms_accepted_at`. Combinado con que los documentos viven en commits inmutables de este repo público, hay prueba completa de qué versión exacta aceptó cada usuario y cuándo.
