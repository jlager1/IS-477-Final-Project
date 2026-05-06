


## Data Collection and Acquisition

The three original datasets that we used in this project were manually downloaded from sources we found online. The datasets contained historical team-level stats for the NFL, NBA, and MLB. Each dataset was downloaded as a CSV file and saved in the project’s raw data folder before any cleaning or merging was performed.

### Acquisition Process

1. Navigate to the online source for the NFL dataset.
2. Download the dataset as a CSV file.
3. Save the file as `nfl_raw.csv` in the `data/raw/` folder.
4. Repeat the same process for the NBA and MLB datasets.
5. Verify the integrity of each downloaded file using SHA-256 checksums.
6. Store the checksum values in `checksums.txt`.

### Raw Data Files

| Dataset | File Name | Source | Date Accessed |
|---|---|---|---|
| NFL team dataset | `nfl_raw.csv` | **[https://www.pro-football-reference.com/teams/](https://www.pro-football-reference.com/teams/https://www.pro-football-reference.com/teams)** |[3/12/2026] |
| NBA team dataset | `nba_raw.csv` | **[https://www.basketball-reference.com/teams/](https://www.basketball-reference.com/teams/)** |[3/12/2026] |
| MLB team dataset | `mlb_raw.csv` | https://www.baseball-reference.com/teams/ |[3/12/2026] |

### Integrity Checks

The following command was used to generate SHA-256 checksums for the raw CSV files:

```bash
shasum -a 256 data/raw/*.csv > checksums.txt
