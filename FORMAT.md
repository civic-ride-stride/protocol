# The message format

> **Status: proposal, open for comment.** Nothing below is final, and nothing
> has been published in this shape. Comment in an issue.

Figures are published on [Nostr](https://github.com/nostr-protocol/nips),
signed by the publisher's key. Nostr is open and decentralised: anyone can read,
no one owns the network, and a publisher's signature shows who made a figure.

**A published event cannot be taken back.** That is why the rules in
[RULES.md](RULES.md) apply before anything is signed, and why each publisher
rehearses on a relay it runs itself before publishing anywhere else.

## One event per cell, per series, per window

An **addressable** event, so a publisher can replace a figure in the same
series without a second version standing beside the first. The event kind is
**not chosen yet** (an addressable kind, 30000–39999); the intent is to propose
it as a NIP once the shape is settled.

```json
{
  "kind": "<to be chosen>",
  "tags": [
    ["d", "<series>:<h3 cell>:<window>"],
    ["series", "example-app/cells-1"],
    ["grid", "h3", "8"],
    ["cell", "881969c9b1fffff"],
    ["window", "2015-01-01/2024-12-31", "working-day", "morning-peak"],
    ["mode", "ride"],
    ["people", "34"],
    ["passages", "512"],
    ["k", "10"],
    ["dominance", "0.5"],
    ["crop", "keyed-uniform", "50", "300", "not-at:train,ferry"],
    ["recipe", "cells-1"]
  ],
  "content": ""
}
```

The values above are an **illustration**, not a published figure. The cell is real —
`881969c9b1fffff`, resolution 8, around Amsterdam Centraal, computed with `h3-js`
4.1.0 — and the publisher and the counts are invented.

## Open questions

- **The kind number**, and whether this becomes a NIP of its own.
- **Dominated cells:** a cell under rule 2 carries `people` only, and no
  `passages`. Is a tag needed to say so, or is the absence enough?
- **Reports:** the category list, and a separate kind.
- **Plans:** a separate kind so a city can publish its own plans beside the
  counts, under the city's own key.
- **Discovery:** how a reader finds every publisher's series.
