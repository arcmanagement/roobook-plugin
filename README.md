# RooBook for Grok Bot

Publisher: ArcManagement Inc., the operator of RooBook (https://roobook.app). Support: support@roobook.app.

Grok Bot installs this plugin from the Cursor Marketplace. After you connect a RooBook account, the bot can list that account's books, search the full text, and save a private reading note.

Server: `https://api.roobook.app/mcp`

Sign-in is OAuth on RooBook (dynamic client registration, PKCE S256, scope `mcp`). The plugin ships no client secret and no password field. Tools run as the account that approved the connection. Another person's library is not reachable from these tools.

## What the bot can call

| Tool | Effect |
| --- | --- |
| `list_books` | List books on the connected account, with EPUB and reader URLs |
| `get_book` | Metadata for one book |
| `search_library` | Full-text search with page, snippet, image coordinates, and a `roobook://` link |
| `add_note` | Save a private note on a book or a page |
| `semantic_search` | Nearest chunks for a supplied embedding. The bundled skill tells the bot not to call this from chat |

Removing the plugin in Grok Bot stops new calls from that installation. RooBook's own account settings stay at [roobook.app](https://roobook.app).

## Policies

- Privacy: https://roobook.app/privacy
- Terms: https://roobook.app/terms
- Support: https://roobook.app/support

The plugin package in this repository is MIT. The RooBook service is covered by the terms above.
