# OpsTrace Analytics

Log analysis tool for industrial machine logs, built with Python, Pandas and Streamlit.

<!-- keep your existing logo line here -->

## Why it exists
A control support engineer in the intralogistics sector had to trace machine errors by opening scattered `.log` and `.txt` files one by one and searching them by hand. OpsTrace merges those files into one dataset and makes it searchable and filterable in the browser, even at 100k+ rows. The tool is in daily use.

## Screenshot
![OpsTrace main view](docs/screenshot.png)
*Synthetic data.*

## Features
- **Multi-file ingestion:** drag and drop several `.log` / `.txt` files; they are merged into one dataset.
- **Time range filtering:** filter by date and time, with UTC normalisation and microsecond timestamps.
- **Keyword search across all columns:** find terms such as "Error", "Fail" or "Exception" in the full dataset.
- **Status filter:** inclusion-based filter (select what to keep), so multi-step filtering does not drop rows by mistake.
- **Large tables:** AgGrid virtualisation and Streamlit caching keep 100k+ rows responsive; rows can be copied to the clipboard.
- **Export:** CSV export in UTF-8-SIG, so reports open correctly in Excel.
- **Simple access control:** password gate based on Streamlit session state.

## How it works
1. **Load:** read and merge the log files.
2. **Transform:** parse timestamps, clean and normalise columns.
3. **Present:** filter, search and export in the browser.

## Tech stack
Python 3 · Pandas · Streamlit · streamlit-aggrid

## Run it locally
```bash
pip install -r requirements.txt
streamlit run app.py
```
On Windows you can also double-click `start.bat`.

## Data
This repository contains no real company data. Sample files are synthetic.

## Changelog
- **v2.1:** copy rows from the grid to the clipboard; microsecond timestamp support.
- **v2.0:** caching for file loading; AgGrid virtualisation for 100k+ rows; keyword search across all columns; Windows launcher.

## License
MIT

Built by Ozan Zeydanoğlu · [LinkedIn](https://www.linkedin.com/in/ozanzeydanoglu/)
