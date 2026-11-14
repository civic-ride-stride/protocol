# The rules

Every publisher follows all of these. They are requirements, not guidelines.
The parameters are **published**, not hidden constants, so anyone can check
them — and every published figure carries them (see "The recipe" below).

## 1. Ten people behind every figure

A figure is published only when **at least ten distinct people** contributed to
it (k = 10). This holds at every resolution and in every breakdown: a cell, a
cell by mode, a cell by time of day, a pair of zones.

Below ten, a figure is **suppressed** or **merged** into a coarser cell or a
longer period. Sparse places — a village lane at night — are never published.
That is the guarantee, not a shortcoming.

**One exception, written as one: messages to a smart traffic light.** *Added
12 November 2026, by the founding publisher.* A smart traffic light (iVRI)
receives a message when an app announces a rider approaching. The message
carries no person, so the people behind a light cannot be counted, and this
rule cannot be checked. A publisher may still publish, per light, **the number
of messages as one total over its whole period, with no time breakdown at
all**, marked `k` = `none` with the reason. The position is the light's. What
turns a quiet light into one person's routine is time — a weekday, a part of
the day — so any breakdown in time falls under this rule again, and messages
cannot meet it.

## 2. No figure that is one person's routine

Ten people can pass a place while one of them makes most of the trips. Where
**one person makes more than half of the trips** in a cell, the cell shows
**how many people passed and nothing else**: no number of trips, no speed, no
waiting time, no breakdown.

*13 November 2026:* the same holds for **every row that counts trips** — a pair
of zones, a station and a zone, a jump between two stations, a band of
distance. Where one person makes more than half of its trips, the row shows its
people only. [Rule 11](#11-a-total-stands-only-where-it-gives-nothing-back)
keeps those trips from coming back through a total.

## 3. The ends of every trip are cut off

Before anything is counted, **each end of each trip is cut** by a length drawn
**at random between 50 and 300 metres**, separately for each end. The length is
not published per trip, so no end can be extended back to a front door.

**Exception:** an end at a **train station or ferry landing** is not cut, because
those are public places shared by many people and the transfer between modes is
part of what cities need to see. An end at a bus, tram or metro stop **is** cut.

## 4. Time is coarse

Time is published as **day type × part of the day** (for example working day,
morning peak) — never a date tied to a person, never a minute. Thin periods are
merged until they hold ten people.

## 5. Rides and strides apart

Cycling (**ride**) and walking (**stride**) are counted and published
separately. A combined figure is published where **every subtraction from it
leaves ten people or more**: take the combined figure, take away every
published figure inside it — the strides, the rides in the smaller cells it
contains — and whatever remains above zero has at least ten people behind it,
for every stretch of the week the published figures can be cut into. Each
publisher shows this with a subtraction test on its own data before its first
publication.

A publisher that runs no such test keeps to the simpler form: a combined
figure only where the rides and the strides each have ten people behind them.

*13 November 2026:* journeys — trips joined at a station, stop or ferry — add
a third mode: the journey that rode one part and walked another. It is
published as a mode of its own, beside rides and strides, and a combined figure
over journeys answers to this rule for all three.

> **Changed 10 November 2026.** The rule used to read: ~~*"A combined figure is
> published only where each part clears the rules on its own."*~~ That form is
> safe, and it protects walkers by leaving the combined figure out wherever
> fewer than ten people walked. The new wording states what is protected —
> whatever any subtraction leaves has ten people or more behind it — and lets
> a test show it, cell by cell. Where walkers are few, the combined figure can
> stand, with them hidden among the riders. The old form stays as the simpler
> form above.

## 6. One source, one series

Each publisher's data is its **own series**. Different apps measure with
different instruments, so series are shown side by side, never summed into one
line — unless each part clears the rules on its own.

**A source id on every message — required.** *Added 13 November 2026; the
founding publisher's requirement of 10 November: "Een bron_iD voor de data is
dan een eis."*

- **What it is:** the first two parts of the message's `d` tag,
  `<publisher>/<source>` — for the founding publisher's V2 archive,
  `ring-ring/v2`. See [FORMAT.md](FORMAT.md).
- **The publisher part** is the same on every message one key signs, and
  belongs to that key alone.
- **The source part** names one source — one app, one archive, one network of
  counters — and is never given to another source by the same publisher.
- **A message without a source id is not part of this protocol**, however good
  its figures.

**Sources stand beside each other.** A person who uses two apps counts once in
each source. No publisher de-duplicates people across sources, and no figure
adds the people of two sources into one count: that would need the very
link between two apps' riders that this protocol keeps from existing.

## 7. A changed method is a new series

When the grid, the resolution, the source, the matcher or a rule changes, the
publisher starts a **new series beside the old one**. Numbers already published
are never silently revised: a reader must always be able to tell whether the
world changed or the method did.

## 8. Reports as counts only

Where people report problems (an unsafe crossing, a missing path), only
**counts per category per place** are published — never the words someone wrote.

## 9. Never individual, never sold

No publisher releases an individual route, trip or person to anyone, and no
publisher sells exclusive access to what it publishes here.

## 10. What is hidden is hidden together

*Rules 10 to 13 added 13 November 2026, from the founding publisher's attack
tests on pairs of zones, journeys, stations and distances. Each closes a way a
figure under ten people came back out of figures that each had ten.*

A figure published as **a list of parts** — an origin's destinations, a
station's zones — shows each part that has ten people, and
puts the rest **together in one row, `other`**. Where that row would hold fewer
than ten people, **the smallest shown part joins it**, then the next, until it
holds ten. Where the whole list holds fewer than ten people, the publisher keeps
all of it back. So whatever a reader subtracts from what, a hidden part stays
inside a group of ten.

## 11. A total stands only where it gives nothing back

[Rule 2](#2-no-figure-that-is-one-persons-routine) holds back a part's trips
where one person makes most of them. A total of the parts would hand those
trips back: the total minus the parts shown. So a list with a part held back
under rule 2 gives its **total as people only**, and its spread — over distance,
over time — **as shares of the trips**. People cannot be subtracted from each
other: the same person can be in several parts.

A national total of trips stands where what it leaves after every published part
spans **at least two** parts held back, so the remainder is never one part's
trips.

## 12. A pair of zones is counted one way

Pairs of zones are published **at one resolution**, and **either as directions**
(from A to B) **or as links** (A and B, either way), one of the two. A coarse
pair minus its fine pairs gives back the fine pairs that were hidden, and a link
minus one direction gives back the other. The founding publisher counts
directions, at H3 resolution 7.

## 13. Shares come complete

Shares that make up a whole — the parts of a day, the bands of a distance — are
published **all together**, each part with ten people behind it, or the row
carries none of them. One part held back while the others are shown would come
back as one hundred minus them.

## 14. Every figure shown with its source

*Added 14 November 2026; the founding publisher's requirement: "Ook voor andere
apps dat de bron_id van de melder zichtbaar blijft" — and of the two ways to
make it so, the one that keeps the figures free of conditions ("A").*

- **Where a publisher shows a figure or a report count** — on a map, in an app,
  in a dashboard — it shows that figure's **source id** with it: its own, and
  every other publisher's. Within one click is enough, such as a card or a
  panel on how the figure was made. Every figure shown under this protocol can
  be traced to its source from where it is shown.
- **A view that combines sources** shows each source beside its own figures, as
  [rule 6](#6-one-source-one-series) asks: one figure, one source.
- **Everyone else is asked, not bound.** The figures carry CC0
  ([FORMAT.md](FORMAT.md)): anyone may use them, for anything, without
  conditions. For a reader outside this protocol — a city's own dashboard, a
  researcher, another map — showing the source is a request. The signature
  keeps every figure traceable all the same: whoever holds a message can check
  which key signed it and which source id it carries.

**Why:** the app that measured is credited for what it measured, a reader can
always tell which instrument a number came from, and a city knows which
publisher to ask about it.

---

## The recipe

Every published figure carries the recipe that made it, as fields on the
message (see [FORMAT.md](FORMAT.md)):

| Field | Example |
|---|---|
| Source id (required) | `ring-ring/v2` — the first two parts of `d` |
| Publisher | `ring-ring` |
| Source and years | `v2-archive 2015–2024` |
| Grid and resolution | `h3 res 8` |
| Threshold | `k=10 people` |
| Dominance rule | `>50% of trips → people only` |
| Crop | `keyed uniform 50–300 m per end, not at train or ferry` |
| Time | `day type × day part` |
| Recipe version | `v2-cells-2` |

A figure without these fields is not part of this protocol.
