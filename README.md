# TV Episode Major Events Dataset

## Overview
This project is a structured dataset analyzing major narrative events across multiple television series at the episode level.  
The goal is to identify and compare the impact of events such as character deaths, exits, premieres, and finales in relation to episode ratings and narrative structure.

The dataset is designed for exploratory data analysis, visualization, and potential machine learning applications involving media analytics and event-driven trends.

---

## Motivation
Most episode datasets only contain ratings and air dates.  
This project extends traditional episode data by introducing **event classification** and **priority logic**, enabling deeper analysis such as:

- Do major character deaths correlate with higher ratings?
- Are finales consistently rated higher than premieres?
- Which shows rely more heavily on event-driven storytelling?
- Event density comparisons across series

---

## Dataset Structure

### `episodes.csv`
Primary fact table containing one row per episode.

| Column | Description |
|--------|------------|
| show_name | Name of the TV series |
| season | Season number |
| episode | Episode number within season |
| air_date | Original air date |
| imdb_rating | IMDb user rating |
| episode_index | Sequential index within show |
| is_event | Binary flag (1 = major event, 0 = none) |
| event_type | Controlled vocabulary category |
| event_detail | Character or description of event |

---

### `data_dictionary.csv`
Defines schema and allowed values for each column.

---

### `event_types.csv`
Controlled vocabulary for event classification.

Example categories:
- `death`
- `exit`
- `series_finale`
- `finale`
- `premiere`

---

### `event_types_priority.csv`
Defines precedence rules when multiple events occur in the same episode.

Example hierarchy:

---

## Methodology & Rules

- Only **one primary event per episode** is logged.
- Events must be **explicit and on-screen**; off-screen or ambiguous deaths are excluded.
- Priority rules determine which event is recorded when multiple occur.
- `is_event = 0` requires `event_type` and `event_detail` to be blank.
- Episode indexing is unique within each show.
- Event types are restricted to the controlled vocabulary table.

---

## Potential Analyses

- Rating spikes associated with major character deaths
- Event density by season or show
- Finale vs premiere rating comparisons
- Character exit frequency
- Event impact regression modeling

---

## Tools Used

- Google Sheets (data entry & cleaning)
- Python / Pandas (planned analysis)
- SQL (planned querying)
- Tableau / Power BI (planned visualization)

---

## Future Improvements

- Additional TV series coverage
- Automated rating scraping
- Character appearance tracking
- Natural language processing on episode summaries

---

## License
MIT License
