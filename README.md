# LogLens

LogLens is a local command-line Python script that counts the records in a CSV log file. It can count every record in the file, or only the records at one log level: `INFO`, `WARN`, or `ERROR`.

## Contents

- [Who this guide is for](#who-this-guide-is-for)
- [LogLens capabilities](#loglens-capabilities)
- [Requirements](#requirements)
- [Quick start](#quick-start)
- [Usage](#usage)
- [Input format](#input-format)
- [Repository files](#repository-files)
- [Getting help](#getting-help)

## Who this guide is for

This guide is for undergraduate computing students and new technical interns who have not used LogLens before. You should know what a CSV file is and have run commands in a terminal. You do not need to know how this repository is organized; this guide will tell you where each file is.

## LogLens capabilities

LogLens:
- Counts the records in a CSV log file. By default, all records are counted but it can be filtered to be only at one log level.
- Runs only on your computer.

LogLens does **not**:
- Repair, rewrite, or otherwise modify your CSV file. It only reads it.
- Upload, transmit, or store your data outside your computer.
- Diagnose system failures or explain why an error occurred. It reports a count based off of log level.

## Requirements

- Python **3.10 or newer.**

> **Note:** The examples in this guide use the command `python`. On some computers, the Python launcher is `python3` or `py` instead. Use whichever one starts Python 3.10 or newer on your computer.

## Quick start

These steps get LogLens running on the included sample file. For detailed setup instructions, see the [installation guide](docs/INSTALL.md).

1. On this repository's GitHub page, select **Code**, then **Download ZIP**. Extract the ZIP file.
2. Open a terminal and move to the **repository root**, which is the extracted folder that contains `loglens.py`:

   ```bash
   cd path/to/extracted-folder
   ```

3. Run LogLens on the sample file:

   ```bash
   python loglens.py --file data/sample_logs.csv --level ERROR
   ```

4. Check the result. If LogLens is working, you will see:

   ```text
   Records matching ERROR: 2
   ```

## Usage

```bash
python loglens.py --file PATH [--level LEVEL]
```

Square brackets mean that there is an optional part of the command, do not type the brackets.

| Option | Required? | Description |
| --- | --- | --- |
| `--file PATH` | Yes | Path to the CSV log file to read. |
| `--level LEVEL` | No | Count only records at this level: `INFO`, `WARN`, or `ERROR`. Type the level in uppercase. If you leave this option out, LogLens counts all records. |
| `--help` | No | List the valid options. |

### Examples



Count all records in the sample file:

```bash
python loglens.py --file data/sample_logs.csv
```

```text
Records matching ALL: 6
```

List the valid options:

```bash
python loglens.py --help
```

To check your own log file, replace `data/sample_logs.csv` with the path to your file. Make sure the file meets the [input format](#input-format) first.

## Input format

LogLens reads CSV files. The first row of the file must contain these three column headers, spelled exactly as shown, in lowercase:

| Column header | What it holds |
| --- | --- |
| `timestamp` | The time of the event |
| `level` | The log level: `INFO`, `WARN`, or `ERROR`, in uppercase |
| `message` | A description of the event |

For an example, see the included sample file, `data/sample_logs.csv`.

## Repository files

| File | Purpose |
| --- | --- |
| `loglens.py` | The LogLens script. Its folder is the repository root. |
| `data/sample_logs.csv` | Sample log file used in the examples. |
| `docs/INSTALL.md` | The [installation guide](docs/INSTALL.md). |

## Getting help

1. Run `python loglens.py --help` to check the valid options.
2. Check that you followed the [installation guide](docs/INSTALL.md) and are running the command from the repository root.
3. If the problem continues, open an issue in this repository. Include the exact command you ran, the full error message, and your Python version.

> **Protect sensitive data:** Do not post sensitive log data in an issue. Describe the problem and, if an example is needed, only include a small sanitized sample with any sensitive values removed.