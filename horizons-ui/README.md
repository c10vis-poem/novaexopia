# horizons-ui — APK 1: Master Visual Presentation Shell (WebView)

Per `05_FEDERATED_FILE_TREE_TOPOLOGY_MASTER.md`, source subfolder
`--•📦HORIZONS_UI_🌐` in `___Lex-Novi-Æxentis-Copiæ` (not yet shared with this
session — content below is sourced from `AUDIT_LEX_NOVI_AESOP_XI.md`, the
accessible audit of the adjacent Æsop-Xi subfolder, which references this one
directly; the dedicated `AUDIT-05-HORIZONS-UI.md` returned a Drive access
error when fetched and was not read).

## What this is

The Chromium WebView shell — the "Four Rooms & Seven-Tile" architecture
referenced in the audit index. Decoupled from the terminal daemon (`aesc`,
separate repo `novus-aesc`) and media daemon (`aeyre`, separate repo
`novus-aeyre`) — this APK is presentation only, talking to both over local
WebSocket bridges (ports 8080 and 8765 per the audit).

## Layout

- `app/src/main/assets/web/` — HTML5/React chat tiles & terminal GUI
- `bridge/` — WebSocket clients to Æsc and Æyre

## Open gap

The full four-rooms/seven-tile spec and the actual WebView/Kotlin scaffolding
are in `AUDIT-05-HORIZONS-UI.md` (Drive id
`1ZaGEDhTlgbfIZN_rkWkSiGUNw42zUuU9RA7XtmdQPT0`), which this session could not
read (entity-not-found on a shared-search hit — likely not actually shared
despite appearing in search). Needs a follow-up read once access is fixed.
