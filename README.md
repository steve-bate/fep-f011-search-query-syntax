# FEP-f011: Full-Text Search Query Syntax for ActivityPub

**Status:** DRAFT · **Type:** implementation · **Author:** Steve Bate · **Received:** 2026-03-17

## Overview

This FEP defines a query syntax for full-text search on ActivityPub search endpoints,
carried in the `q` query parameter of a URI advertised via the actor's `endpoints.search`
property. The syntax covers:

- Terms and quoted phrases
- Faceted search (`facet:value`), where the facet is typically a JSON property path
- Boolean operators (`AND`, `OR`, `NOT`) and parenthesized groups
- Implicit `AND` between adjacent expressions
- Regex literals (`/.../`), recommended to follow RFC 9485 I-Regexp
- Inclusive, exclusive, and mixed range bounds (`[a TO b]`, `{a TO b}`, `[a TO b}`)

Operator precedence runs from parentheses through unary `NOT`, `AND` (explicit or implicit),
and `OR`, with `AND`/`OR` left-associative. Results are returned as an ActivityPub `Collection`
or `OrderedCollection`; the FEP standardizes syntax and parsing behavior rather than ranking or
scoring. The file [`fep-f011.abnf`](fep-f011.abnf) contains the complete ABNF grammar.

## Files

- [`fep-f011.md`](fep-f011.md) — the proposal
- [`fep-f011.abnf`](fep-f011.abnf) — full ABNF grammar
- [`fep-f011.jsonld`](fep-f011.jsonld) — JSON-LD context

## The FEP

- Document: <https://github.com/steve-bate/fep-f011-search-query-syntax/blob/main/fep-f011.md>
- Repository: <https://github.com/steve-bate/fep-f011-search-query-syntax>
- Discussion: <https://github.com/steve-bate/fep-f011-search-query-syntax/issues>

## License

This work is released under [CC0 1.0 Universal](LICENSE.md) (public domain dedication).
See [LICENSE.md](LICENSE.md).
