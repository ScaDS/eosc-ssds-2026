# Data Dictionary for `field_samples_raw.csv`

> The **intended clean schema** for the raw field-samples dataset.  
> This is the reference both validation (pandera) and packaging (frictionless) work toward.  
> The raw file deliberately violates several of these rules.

| Field | Type | Required | Unique | Constraints / Allowed values | Unit | Description |
|---|---|---|---|---|---|---|
| `sample_id` | string | yes | yes | Pattern `S####` (e.g. `S0001`); no leading/trailing whitespace | – | Unique identifier for each collected sample. **Primary key.** |
| `species` | categorical | yes | no | One of: `Adelie`, `Chinstrap`, `Gentoo` | – | Penguin species. Controlled vocabulary; case-sensitive. |
| `island` | categorical | yes | no | One of: `Biscoe`, `Dream`, `Torgersen` | – | Island in the Palmer Archipelago where the sample was collected. |
| `date_collected` | date | yes | no | ISO 8601 `YYYY-MM-DD` | – | Date the sample was collected. |
| `body_mass_g` | integer | yes | no | 2500–6500 | grams (g) | Body mass of the individual. |
| `flipper_length_mm` | number | yes | no | 150.0–250.0 | millimetres (mm) | Flipper length of the individual. |
| `sex` | categorical | no | no | One of: `male`, `female` (empty = unknown/not recorded) | – | Recorded sex of the individual. |
| `region` | string | yes | no | Constant: `Antarctica` | – | Broad geographic region. Constant across the dataset. |
| `notes` | string | no | no | Free text | – | Optional field-collection remarks. |

## Notes on the controlled vocabularies

- **`species`**: three valid categories. The raw data mixes casing (`adelie`, `ADELIE`),
  adds whitespace (`Adelie `), uses a long form (`Chinstrap Penguin`) and a typo (`Gentooo`).
- **`island`**: three valid categories. The raw data contains the typo `Bisco` and blanks.
- **`sex`**: should resolve to `male` / `female`; the raw data uses `M`, `MALE`, `female`,
  `.`, `unknown`, and blanks.

## Missing-value policy

In the clean dataset, missing values are represented as **empty cells** (read as `NaN`).
The raw file encodes "missing" inconsistently as `""`, `NA`, `n/a`, `-999`, `NULL`, and `?`.
All of these must be normalised to a single missing representation before validation.

## Known transformations needed (raw to clean)

1. Strip whitespace and normalise casing in `sample_id`, `species`, `island`, `sex`.
2. Map category variants to the controlled vocabularies above.
3. Parse `body_mass_g` to integer: strip ` g` unit, treat `-999` as missing,
   flag impossible values (negatives, > 6500).
4. Parse `flipper_length_mm` to number: convert comma-decimals (`195,5` → `195.5`),
   flag cm-vs-mm outliers (~10× too large).
5. Parse the four `date_collected` formats into ISO 8601.
6. Drop exact duplicate rows.
7. Decide whether to keep the constant `region` column.
