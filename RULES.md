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

## 2. No figure that is one person's routine

Ten people can pass a place while one of them makes most of the trips. Where
**one person makes more than half of the trips** in a cell, the cell shows
**how many people passed and nothing else**: no number of trips, no speed, no
waiting time, no breakdown.

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

---

## The recipe

Every published figure carries the recipe that made it, as fields on the
message (see [FORMAT.md](FORMAT.md)):

| Field | Example |
|---|---|
| Publisher | `ring-ring` |
| Source and years | `v2-archive 2015–2024` |
| Grid and resolution | `h3 res 8` |
| Threshold | `k=10 people` |
| Dominance rule | `>50% of trips → people only` |
| Crop | `keyed uniform 50–300 m per end, not at train or ferry` |
| Time | `day type × day part` |
| Recipe version | `v2-cells-2` |

A figure without these fields is not part of this protocol.
