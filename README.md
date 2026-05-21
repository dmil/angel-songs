# Angel Songs

An investigation into how often songs with "Angel" in the title have been released over time, across multiple music datasets.

> 🤖 This document is an AI-generated summary of exploratory data analysis conducted with Claude. Charts and findings were produced interactively and may reflect dataset biases.

---

## Methodology

For each data source, we produced three charts:
1. **All songs by year** — total song releases per year in the dataset
2. **Angel songs by year** — songs with "angel" (case-insensitive) in the title, per year
3. **Angel song rate** — angel songs as a share of all songs that year

---

## Sources

### MusicBrainz
**Full export, May 2026** · [musicbrainz.org](https://musicbrainz.org)

A comprehensive open music encyclopedia with ~38.9 million recordings, 5.5 million releases, and 55.9 million tracks. Dates come from `release_country` and `release_unknown_country` tables. The largest and most complete dataset here.

| Chart | File |
|-------|------|
| All songs by year | `musicbrainz/songs_by_year.png` |
| Angel songs by year | `musicbrainz/angel_songs_by_year.png` |
| Angel song rate | `musicbrainz/angel_song_rate.png` |

Scripts: `musicbrainz/songs_by_year.R`, `musicbrainz/angel_songs_by_year.R`, `musicbrainz/angel_song_rate.R`

---

### Million Song Dataset
**millionsongdataset.com**

A collection of audio features and metadata for one million contemporary popular music tracks. ~515K of the 1M tracks have year data. Source file: `msd_summary_file.h5` (HDF5 format). Titles and years extracted via `export_csv.py`.

| Chart | File |
|-------|------|
| All songs by year | `million-songs-database/all_songs_by_year.png` |
| Angel songs by year | `million-songs-database/angel_songs_by_year.png` |
| Angel song rate | `million-songs-database/angel_song_rate.png` |

Scripts: `million-songs-database/export_csv.py`, `million-songs-database/charts.R`

---

### Kaggle Spotify Music Info
**Kaggle Spotify dataset**

A Kaggle dataset of songs with Spotify audio features (danceability, energy, tempo, etc.) and year metadata. Contains track names and release years.

| Chart | File |
|-------|------|
| All songs by year | `kaggle-spotify/all_songs_by_year.png` |
| Angel songs by year | `kaggle-spotify/angel_songs_by_year.png` |
| Angel song rate | `kaggle-spotify/angel_song_rate.png` |

Script: `kaggle-spotify/charts.R`

---

### Kaggle Billboard #1 Hits
**Scraped via Genius / Billboard**

#1 charting songs scraped from a Billboard chart archive, enriched with lyrics via Genius. ~6,500 songs from 1958 to present. Scraped using `kaggle-top-100/scraper.py`.

| Chart | File |
|-------|------|
| All songs by year | `kaggle-top-100/all_songs_by_year.png` |
| Angel songs by year | `kaggle-top-100/angel_songs_by_year.png` |
| Angel song rate | `kaggle-top-100/angel_song_rate.png` |

Script: `kaggle-top-100/charts.R`
