# The message format

> **Status: proposal, open for comment.** Nothing below is final, and nothing
> has been published in this shape. Comment in an issue.

Figures are published on [Nostr](https://github.com/nostr-protocol/nips),
signed by the publisher's key. Nostr is open and decentralised: anyone can read,
no one owns the network, and a publisher's signature shows who made a figure.

**A published event cannot be taken back.** That is why the rules in
[RULES.md](RULES.md) apply before anything is signed, and why each publisher
rehearses on a relay it runs itself before publishing anywhere else.

## One event per area, per series

> **Changed 10 November 2026.** This section read *"One event per cell, per
> series, per window"*. A map shows hundreds of thousands of cells, and a
> browser cannot fetch that many events; it can fetch a few thousand. So an
> event now holds every published cell of one **area**, an H3 hexagon at
> resolution 6 (about 36 km², 7 km across). The area is the envelope, not the
> lens: inside it every cell keeps its own resolution, so a map still zooms to
> the street.

An **addressable** event, so a series can be found and read by its `d` tag.
The event kind for this protocol is **not chosen yet** (an addressable kind,
30000–39999), and the intent is to propose it as a NIP once the shape is
settled. Meanwhile the founding publisher uses **30078** (NIP-78).

- **One series, one area, one event**, cut into numbered parts when the area
  is too large for one event (relays commonly take up to 64 KiB). A cell's
  rows always stay in one part.
- **The ingredients are tags on every event**, so each event says how its
  figures were made without a reader fetching anything else.
- **Published once.** `created_at` is the time the publisher made the series.
  A changed method is a new series beside the old one ([rule 7](RULES.md)),
  never a new version of the same events.

```json
{
  "kind": 30078,
  "created_at": 1762700000,
  "tags": [
    ["d", "example-app/cells-1/rides/861969c9fffffff/1"],
    ["series", "cells-1/rides"],
    ["source", "example-app", "2025", "2026"],
    ["recipe", "cells-1 k=10 rides=res10 ladder=per-day>weekday-weekend>week blocks=5,merged-to-k"],
    ["grid", "h3", "10"],
    ["area", "861969c9fffffff", "6"],
    ["mode", "ride"],
    ["k", "10"],
    ["dominance", "0.5", "passages-withheld"],
    ["crop", "keyed-uniform", "50", "300", "not-at:train,ferry"],
    ["time", "weekday-ladder", "per-day>weekday-weekend>week"],
    ["blocks", "07-09", "09-16", "16-19", "19-24", "00-07"],
    ["part", "1", "1"],
    ["license", "CC0-1.0"],
    ["alt", "Example app open data: rides in one area, every figure standing for at least 10 people"]
  ],
  "content": "{\"columns\":[\"cell\",\"rung\",\"day\",\"from\",\"to\",\"people\",\"passages\"],\"rows\":[[\"8a1969c9b007fff\",\"weekday-weekend\",\"weekday\",0,5,34,512],[\"8a1969c9b007fff\",\"weekday-weekend\",\"weekend\",1,3,11,null]]}"
}
```

The values above are an **illustration**, not a published figure. The area
`861969c9fffffff` (resolution 6) and the cell `8a1969c9b007fff` (resolution 10)
are real, computed with `h3` 4.x around Amsterdam Centraal; the publisher and
the counts are invented.

**The rows.** Each row is one cell on its own rung of the time ladder
([rule 4](RULES.md)): `rung` is `per-day`, `weekday-weekend` or `week`; `day`
is `mon` to `sun`, `weekday`, `weekend` or `week`; `from` and `to` index the
`blocks` tag, `to` exclusive; `passages` is `null` where one person makes more
than half of them ([rule 2](RULES.md)).

## Open questions

- **The kind number**, and whether this becomes a NIP of its own.
- ~~**Dominated cells:** a cell under rule 2 carries `people` only, and no
  `passages`. Is a tag needed to say so, or is the absence enough?~~
  *Answered 10 November 2026:* `passages` is `null` in the row, and the
  `dominance` tag says why.
- **Reports:** the category list, and a separate kind.
- **Plans:** a separate kind so a city can publish its own plans beside the
  counts, under the city's own key.
- **Discovery:** how a reader finds every publisher's series.
