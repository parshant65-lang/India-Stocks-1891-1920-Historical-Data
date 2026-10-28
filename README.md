# India-Stocks-1891-1920-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1891 to 1920)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1891-1920-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1891 to 1920)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1891 | `PITTIENG` | Pitti Engineering Limited | `PITTIENG.NS` |
| 1892 | `PIXTRANS` | Pix Transmissions Limited | `PIXTRANS.NS` |
| 1893 | `PKTEA` | The Peria Karamalai Tea & Produce Company Limited | `PKTEA.NS` |
| 1894 | `PLASTIBLEN` | Plastiblends India Limited | `PLASTIBLEN.NS` |
| 1895 | `PLATIND` | Platinum Industries Limited | `PLATIND.NS` |
| 1896 | `PLAZACABLE` | Plaza Wires Limited | `PLAZACABLE.NS` |
| 1897 | `PML` | Paul Merchants Limited | `PML.NS` |
| 1898 | `PNBGILTS` | PNB Gilts Limited | `PNBGILTS.NS` |
| 1899 | `PNC` | PNC Media and Entertainment Limited | `PNC.NS` |
| 1900 | `PNCINFRA` | PNC Infratech Limited | `PNCINFRA.NS` |
| 1901 | `PNGJL` | P N Gadgil Jewellers Limited | `PNGJL.NS` |
| 1902 | `PNGSREVA` | PNGS Reva Diamond Jewellery Limited | `PNGSREVA.NS` |
| 1903 | `POCL` | Pondy Oxides & Chemicals Limited | `POCL.NS` |
| 1904 | `PODDARMENT` | Poddar Pigments Limited | `PODDARMENT.NS` |
| 1905 | `POEL` | POCL Enterprises Limited | `POEL.NS` |
| 1906 | `POKARNA` | Pokarna Limited | `POKARNA.NS` |
| 1907 | `POLYPLEX` | Polyplex Corporation Limited | `POLYPLEX.NS` |
| 1908 | `POLYSPIN` | Polyspin Exports Limited | `POLYSPIN.NS` |
| 1909 | `PONNIERODE` | Ponni Sugars (Erode) Limited | `PONNIERODE.NS` |
| 1910 | `POWERICA` | Powerica Limited | `POWERICA.NS` |
| 1911 | `POWERMECH` | Power Mech Projects Limited | `POWERMECH.NS` |
| 1912 | `PPAP` | PPAP Automotive Limited | `PPAP.NS` |
| 1913 | `PPL` | Prakash Pipes Limited | `PPL.NS` |
| 1914 | `PRABHA` | Prabha Energy Limited | `PRABHA.NS` |
| 1915 | `PRADPME` | Pradeep Metals Limited | `PRADPME.NS` |
| 1916 | `PRAENG` | Prajay Engineers Syndicate Limited | `PRAENG.NS` |
| 1917 | `PRAJIND` | Praj Industries Limited | `PRAJIND.NS` |
| 1918 | `PRAKASH` | Prakash Industries Limited | `PRAKASH.NS` |
| 1919 | `PRAKASHSTL` | Prakash Steelage Limited | `PRAKASHSTL.NS` |
| 1920 | `PRANAV` | Pranav Constructions Limited | `PRANAV.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream PITTIENG 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1891-1920-Historical-Data/main/PITTIENG/1m/2026/10/PITTIENG_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
