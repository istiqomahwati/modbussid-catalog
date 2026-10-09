# modbussid-catalog

Remote mod catalog for the **Mod BUSSID Truk, Bus & Travel** Android app
(`com.saedigital.mod.bussid.truck.travel`). The app reads:

```
https://raw.githubusercontent.com/istiqomahwati/modbussid-catalog/main/catalog.json
```

Edit `catalog.json` here and every app picks up the change on next launch / pull-to-refresh — no app update needed.

## Rules

- **Bump `version`** whenever you edit. The app ignores a catalog older than the one it already has.
- `id` must be unique and never change (favorites and installed state use it).
- Always fill `creator` and `sourceUrl` (credit). Use `"Tidak diketahui"` if the creator is unknown.
- **Removal requests:** delete the mod's entry, bump `version`, commit. It disappears from all apps.
- Official Maleo mods use `"resolver": "bussid_official"` (downloaded from bussimulator.id). Never re-upload their files.
- `contactEmail` is shown in the app for content-removal requests.

## Mod entry

```json
{
  "id": "truk-trailer",
  "title": "Truk Trailer",
  "category": "truk",               // truk | bus | travel | mobil | motor | map
  "creator": "Maleo (Kernet)",
  "official": true,
  "description": "…",
  "images": ["https://…/front.jpg", "https://…/back.jpg"],
  "tags": ["trailer", "truk"],
  "sourceUrl": "https://…",         // original page, shown as credit
  "files": [                        // empty = only "Buka Halaman Sumber"
    {
      "label": "File Mod",
      "kind": "mod",                // mod → Documents/BUSSID/Mods, livery → Pictures/BUSSID
      "fileName": "truk-trailer.bussidmod",
      "url": "https://…",           // direct link (e.g. GitHub Release asset)
      "sizeBytes": 11659519,
      "resolver": "direct"          // direct | bussid_official
    }
  ],
  "addedAt": "2026-10-09"
}
```

To host a mod file yourself (with the creator's permission): upload the `.bussidmod` to a GitHub Release
in this repo and use its download URL with `"resolver": "direct"`.
