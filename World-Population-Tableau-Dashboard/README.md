# World Population Tableau Dashboard

A Tableau project that visualizes world population by country from 1970 to 2022.

## Dataset
- File: `data/World_Population_Live_Dataset.csv`
- 234 countries/territories, 15 columns
- Population values are in **thousands** (e.g. China 2022 = 1,425,887 → ~1.43 billion)

| Column | Meaning |
|---|---|
| CCA3 | Country code (2-letter) |
| Name | Country / territory |
| 2022, 2020, 2015, 2010, 2000, 1990, 1980, 1970 | Population (thousands) |
| Area (km²) | Land area |
| Density (per km²) | Population density |
| GrowthRate | Yearly growth rate |
| World Population Percentage | Share of world population |
| Rank | Rank by 2022 population |

## Project Files
```
├── data/World_Population_Live_Dataset.csv
├── tableau/World_population_Data.twbx
├── README.md
└── LICENSE
```

## How to Open
1. Install [Tableau Public](https://public.tableau.com/) (free) or Tableau Desktop.
2. Open `tableau/World_population_Data.twbx`.

## Notes
- Total 2022 population in the dataset ≈ 7.97 billion.
- Namibia's country code is `NA`; some tools read it as an empty value. In pandas, use `keep_default_na=False`.

## Author
Smash — [GitHub](https://github.com/)

## License
All Rights Reserved. See [LICENSE](LICENSE).
