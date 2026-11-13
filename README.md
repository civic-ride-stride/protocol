# CIVIC Ride & Stride

**A civic data platform, powered by we the people, to improve and build walking
and cycling infrastructure.**

People already ride and stride every day. Their trips show where walking and
cycling space works and where it does not — but only if those trips can be
shared without anyone being followed. This repository holds the open rules and
the message format that make that possible, so any app with reliable data can
publish counts that a city, a researcher or a neighbour can check.

> **Status: draft.** The rules in [RULES.md](RULES.md) are settled for the
> founding publisher. The message format in [FORMAT.md](FORMAT.md) is a
> proposal, open for comment. ~~**Nothing has been published under this protocol
> yet.**~~
>
> *10 November 2026:* **the founding publisher's first series is on its own
> relay**, `wss://relay.ring-ring.nu`, in the shape FORMAT.md proposes: Ring-Ring's
> V2 archive, 2015–2024, rides per street and strides per district, signed by
> `npub1qelm78580jyv3f4m2qp4gy5pasxnp57unggzcguj22rltew3xdrsfhl9zl`
> (*CIVIC Ride & Stride · Ring-Ring®*). Not yet on the public relays.
>
> *13 November 2026:* beside it, on the same relay: speed and waiting per
> street, the messages to smart traffic lights, origin and destination per
> zone, distances, stations and their zones, journeys and their jumps by train
> or ferry, an overview of the whole country, and the commuting window per
> distance. Every message carries its recipe, and every series was tested for
> the ways a figure under ten people could come back out before it went out
> ([RULES.md](RULES.md), rules 10–13). The public relays are the next step.

## In one paragraph

Every published figure has **at least ten people behind it**. **The ends of
every trip are cut off** before anything is counted, so no front door is ever
on the map. **The method travels with every number** — which source, which
grid, which rules — so anyone can see how a figure was made, and a changed
method starts a new series instead of quietly rewriting an old one. Counts are
published on an open, decentralised protocol (Nostr), signed by the publisher,
readable by anyone, owned by no one.

## The four principles

1. **Counts, never routes.** No trip, no trace and no person leaves a
   publisher. Only counts per cell of a uniform global grid (H3). *Since 13
   November 2026 also per pair of cells, and per station or ferry landing —
   public places shared by many, as [RULES.md](RULES.md) rule 3 says.*
2. **Ten people or nothing.** A figure with fewer than ten people behind it is
   not published, at any resolution, in any breakdown. *One exception, since 12
   November 2026, in [RULES.md](RULES.md) rule 1: messages to a smart traffic
   light, which carry no person, as one total per light with no time.*
3. **The method on every number.** A figure without its recipe is a number
   nobody can check.
4. **Open to all, sold to no one.** Anyone may read every figure. No publisher
   sells exclusive access to what is published here.

## Join

**Any app or organisation with reliable walking or cycling data is welcome.**

- **What you commit to:** the rules in [RULES.md](RULES.md) — at least ten
  people per figure, hidden parts kept together, trip ends cut off, the recipe
  on every figure, never an individual route, never resale.
- **What you get:** your counts on the shared map beside everyone else's, with
  your name on your recipe, and a series cities can plan against.
- **How, today:** help shape the rules and the format. Open an issue, or
  comment on one. **Publishing comes later**, once the format is settled and
  each publisher has done its own data protection impact assessment.

See [JOIN.md](JOIN.md).

## Who is behind this

Founded by [Ring-Ring](https://ring-ring.nu), a steward-owned company that has
rewarded walking and cycling for more than ten years. Ring-Ring is the first publisher, not
the owner: the rules are meant to outlive any single app, and governance opens
up as publishers join.

## Licence

**Text** (rules, format, documents): [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
**Code** (validators, libraries, examples): [Apache 2.0](LICENSE-APACHE), which includes a
patent grant from every contributor. See [LICENSE](LICENSE).
