# Billboard Year-End Hot 100 Lyrics Dataset (2000–2024)

A curated dataset of song lyrics from the **Billboard Year-End Hot 100** chart, covering 25 years of popular music in the United States.

## Overview

| Field | Details |
|---|---|
| **Coverage** | 2000 – 2024 |
| **Songs** | 2,642 |
| **Language** | English |
| **Source** | Billboard Year-End Hot 100 + Genius API |
| **Format** | CSV (one file per year) |

## Dataset Structure

Each file follows the naming convention `billboard-year-end-YYYY-lyrics.csv` and contains the following columns:

| Column | Type | Description |
|---|---|---|
| `Rank` | integer | Chart position (1–100) |
| `Musica` | string | Song title |
| `Artista` | string | Artist name |
| `Letra` | string | Full song lyrics (retrieved via Genius API) |

## Usage

```python
import pandas as pd
import glob

# Load all years
files = sorted(glob.glob("billboard-year-end-*-lyrics.csv"))
df = pd.concat([pd.read_csv(f) for f in files], ignore_index=True)

# Load a single year
df_2023 = pd.read_csv("billboard-year-end-2023-lyrics.csv")
print(df_2023.head())
```

## Related Publication

This dataset was used in the following paper, accepted at **BreSci 2026** (XX Brazilian e-Science Workshop, co-located with SBBD 2026):

> Tiago de Melo. **Cross-Provider Consistency of LLM-Based Semantic Enrichment for e-Science Workflows.** In: *Proceedings of the XX Brazilian e-Science Workshop (BreSci 2026)*. SBC Open Lib, 2026.

The study evaluates five large language models (ChatGPT, Gemini, DeepSeek, Mistral, and Claude) as interchangeable semantic enrichment components, using the 2000–2023 subset of this dataset (2,387 songs) to classify lyrics into thematic categories and assess cross-provider consistency.

## License

Lyrics are the intellectual property of their respective authors and rights holders. This dataset is shared for **non-commercial research and educational purposes only**, in accordance with fair use principles. If you use this dataset, please cite the paper above.

## Contact

Tiago de Melo — [tmelo@uea.edu.br](mailto:tmelo@uea.edu.br)  
Escola Superior de Tecnologia, Universidade do Estado do Amazonas (UEA), Manaus, Brazil
