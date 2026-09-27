# Homework 4 - Unix Commands & MLP

## Dataset size

The dataset contains 36,859 data records and 36,860 lines including the header.

## Dataset structure

The CSV contains four fields:

- `title` - episode title
- `writer` - writer information
- `pony` - pony/character associated with the dialogue
- `dialog` - dialogue text

The dataset contains 197 unique episode titles.

There are 842 unique values in the `pony` field.

## Unexpected aspect

One unexpected aspect is that the `pony` field has a large number of different values (842), including character names and the entry `Others`. In addition, the CSV contains quoted fields with commas inside the text. Therefore, simple comma-based commands such as `cut -d','` can split records incorrectly. A CSV-aware parser is needed for accurate analysis.

## Task 4

The pony line counts and percentages are:

| Pony | Total line count | Percent of all lines |
|---|---:|---:|
| Twilight Sparkle | 4745 | 12.87% |
| Rarity | 2660 | 7.22% |
| Pinkie Pie | 2833 | 7.69% |
| Rainbow Dash | 3072 | 8.33% |
| Fluttershy | 2109 | 5.72% |

## Commands used

```bash
head -5 clean_dialog.csv
wc -l clean_dialog.csv
tail -n +2 clean_dialog.csv | cut -d',' -f1 | sort -u | wc -l
grep -c 'Twilight Sparkle' clean_dialog.csv
grep -c 'Rarity' clean_dialog.csv
grep -c 'Pinkie Pie' clean_dialog.csv
grep -c 'Rainbow Dash' clean_dialog.csv
grep -c 'Fluttershy' clean_dialog.csv


```
