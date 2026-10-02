---
name: use-roobook
description: Search the signed-in user's RooBook library and cite page-level evidence. Use when the user asks about their own books, pages, quotes, or reading notes.
---

# Use RooBook

Call the `roobook` MCP server. It only sees the RooBook account connected to this plugin.

## Which tool

- Shelf or "what books do I have" → `list_books`
- One book's metadata, EPUB URL, or reader URL → `get_book` with the `bookId` from `list_books`
- A word, phrase, or "where does this appear" → `search_library`
- "Remember this" or "add a note" → `add_note` after you know the `bookId`

Do not call `semantic_search`. It requires an embedding vector this chat does not have. Full-text search is `search_library`.

## How to answer

Quote the returned page number, snippet, and `roobook://` link when they are present. Do not invent a page or a coordinate. If the server returns no hit, say the connected library has no match.

`add_note` writes a private note on that account. Confirm the book and the page with the user before calling it.
