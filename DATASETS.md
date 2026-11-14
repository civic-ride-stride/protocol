# Datasets

Every dataset in one list, in two kinds:

- **Published under this protocol.** Figures signed by a publisher's key, at
  least ten people behind each, the recipe on every message, licence CC0. The
  rules are in [RULES.md](RULES.md); the shape of a message is in
  [FORMAT.md](FORMAT.md).
- **Open data of others.** Datasets a map may show beside those figures, as a
  layer to switch on and off. Each is read from its own publisher, under that
  publisher's licence and with the attribution it asks for. They stay their
  publisher's own: never signed with a protocol key, never mixed into a
  protocol figure ([rule 6](RULES.md#6-one-source-one-series),
  [rule 14](RULES.md#14-every-figure-shown-with-its-source)).

*Started 14 November 2026.*

## Published under this protocol

### `ring-ring/v2` — Ring-Ring V2, 2015–2024

Cycling and walking with the Ring-Ring app in the Netherlands and around it,
2015–2024: 14,756 people who rode and 8,226 who walked.

| | |
|---|---|
| **Source id** | `ring-ring/v2` |
| **Publisher** | Ring-Ring® B.V., the founding publisher |
| **Key** | *CIVIC Ride & Stride · Ring-Ring®*, `npub1qelm78580jyv3f4m2qp4gy5pasxnp57unggzcguj22rltew3xdrsfhl9zl`, NIP-05 `civic@ring-ring.nu` |
| **Relay** | `wss://relay.ring-ring.nu`. The public relays are the next step |
| **Kind** | 30078 |
| **Address** | `d` = `ring-ring/v2/<series>/<area>/<part>`, for example `ring-ring/v2/v2-overview-1/totals/all/1` |
| **Licence** | CC0-1.0, on every message |
| **Published** | once, 10–13 November 2026; a changed method becomes a new series ([rule 7](RULES.md#7-a-changed-method-is-a-new-series)) |
| **On a map** | [portal.ring-ring.nu/nl/open-data](https://portal.ring-ring.nu/nl/open-data) ([English](https://portal.ring-ring.nu/en/open-data)) |

| Series | What a row holds | Messages |
|---|---|---:|
| `v2-export-3` rides, strides | people, and passages where no one person makes most of them, per street (rides, about 120 m) or district (strides, about 850 m), per step of the week and block of the day | 4,161 + 1,476 |
| `v2-ivri-1` | messages received per smart traffic light, one total for June 2020 – July 2024 ([rule 1](RULES.md#1-ten-people-behind-every-figure)) | 1 |
| `v2-speed-1` rides, strides | speed p50 and p85 per street; speed, stopping and waiting as shares | 2,474 + 1,037 |
| `v2-od-1` rides, strides | from a zone of about 5 km² to another: people, and trips | 1,656 + 1,432 |
| `v2-dist-1` rides, strides | a zone's trips by distance, as shares | 1,594 + 1,381 |
| `v2-station-1` rides, strides | a station or ferry landing and the zones its people came from and went to | 3 + 1 |
| `v2-journey-1` rides, strides, mixed | as `v2-od-1`, for trips joined at a station, stop or ferry | 1,471 + 754 + 75 |
| `v2-leg-1` rides, strides, mixed | jumps by public transport between two stations or stops | 1 + 1 + 1 |
| `v2-places-1` | the name and position of every station, stop or ferry landing named above | 1 |
| `v2-overview-1` | per mode the country's people, trips, kilometers and journeys; people per hexagon of about 250 km² | 3 |
| `v2-commute-1` | per mode and distance band, the shares of trips in the commuting window, the rest of the working day and the weekend | 1 |
| | **Together** | **17,524** |

## Open data of others

Candidates for layers beside the protocol's figures. **None is on a map yet.**
Each would be a layer of its own, read from its publisher and carrying that
publisher's credit. Every licence below was read at the publisher, or at
data.overheid.nl, on 14 November 2026.

| Dataset | Publisher | Licence | Credit required | What it adds | Link |
|---|---|---|---|---|---|
| Bicycle counts and count locations | NDW | CC0 1.0, NDW's terms for its open data unless a dataset says otherwise | No; NDW appreciates it | How many cyclists pass a fixed point | [docs.ndw.nu](https://docs.ndw.nu/en/producten/fietsdata/), [terms](https://docs.ndw.nu/algemeen/data-gebruiksvoorwaarden) |
| Road works and events (Melvin) | NDW | CC0 1.0, as above | No | Planned works and closures | [opendata.ndw.nu](https://opendata.ndw.nu/) |
| Registered road accidents (BRON) | Rijkswaterstaat | Public domain (yearly files); CC0 1.0 (*Ongevallen (RWS)*) | No | Where accidents were registered | [BRON](https://data.overheid.nl/dataset/9841-verkeersongevallen---bestand-geregistreerde-ongevallen-nederland), [Ongevallen (RWS)](https://data.overheid.nl/dataset/53580-verkeersongevallen-nederland----ongevallen--rws-) |
| Bicycle counts, Utrecht | Gemeente Utrecht | CC0 1.0 | No | Counts at the city's own points; last updated 11 April 2022 | [data.overheid.nl](https://data.overheid.nl/dataset/utrecht-fietstellingen) |
| Districts and neighbourhoods (Wijk- en buurtkaart 2024) | CBS | CC BY 4.0 | Yes: CBS | Borders and key figures per district and neighbourhood | [data.overheid.nl](https://data.overheid.nl/dataset/71520-wijk--en-buurtkaart-2024-versie-1) |
| Statistics per square, 500 m and 100 m | CBS | Reuse allowed with CBS named as source; CBS's site is CC BY 4.0 | Yes: CBS | Residents and homes per square | [cbs.nl](https://www.cbs.nl/nl-nl/dossier/nederland-regionaal/geografische-data/kaart-van-500-meter-bij-500-meter-met-statistieken), [copyright](https://www.cbs.nl/nl-nl/over-ons/website/copyright) |
| National road database (NWB) | Rijkswaterstaat | CC0 1.0 | No | The road network, with hectometre points | [data.overheid.nl](https://data.overheid.nl/dataset/14767-nwb---wegen) |
| OpenStreetMap | OpenStreetMap Foundation and contributors | ODbL 1.0; a derived database is ODbL too | Yes: © OpenStreetMap contributors | Cycle paths, footpaths, bicycle parking | [copyright](https://www.openstreetmap.org/copyright) |
| Hourly weather observations | KNMI | CC BY 4.0 | Yes: KNMI | The weather beside the ride counts; the API needs a key | [dataplatform.knmi.nl](https://dataplatform.knmi.nl/dataset/hourly-in-situ-meteorological-observations-validated-1-0) |
| Public transport stops (NDOV Loket) | REISinformatiegroep | CC0, its open-data licence | No | Stops and stations | [licence](https://reisinformatiegroep.nl/ndovloket/sla) |
| OV-fiets availability (GBFS) | NS, via openOV | CC BY-SA 3.0 NL, from the feed itself; share-alike | Yes | Bicycles available per station | [feed](https://gbfs.openov.nl/ovfiets/gbfs.json) |
| Donkey Republic, Den Haag (GBFS) | Donkey Republic | CC0 1.0, from the feed itself | No | Shared bicycles per hub | [feed](https://stables.donkey.bike/api/public/gbfs/2/donkey_den_haag/gbfs.json) |

**Checked and left out for now:**

- **NS API** (stations, travel information): NS's own terms — a key, no NS
  logo, access that can end at any time — and no open licence.
- **CROW dashboard deelmobiliteit**: no public terms found.
- **Fietstelweek 2015–2016**: no download or licence found.

**Licences side by side.** Share-alike data (OpenStreetMap, OV-fiets) stays a
layer of its own, with its own credit, beside the protocol's CC0 figures and
never merged into them.

## Adding a dataset

- **To publish under this protocol:** see [JOIN.md](JOIN.md).
- **To list open data of your own:** open an issue with the dataset's link and
  its licence. It is listed here with its publisher, its licence and the
  attribution the publisher asks for.
