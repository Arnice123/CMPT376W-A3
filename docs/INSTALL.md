# LogLens Setup and Usage Guide

This guide explains how to obtain LogLens, locate the repository root, verify that the script runs on your computer, and troubleshoot common setup issues. It is written for undergraduate computing students and new technical interns who understand basic CSV files and have used a terminal, without assuming prior familiarity with this repository.

For an overview of LogLens capabilities, command-line options, and CSV format rules, see the [README](../README.md).

## Contents

- [Before you begin](#before-you-begin)
- [Getting the files](#getting-the-files)
- [Verifying your setup](#verifying-your-setup)
- [Troubleshooting](#troubleshooting)
- [Reporting issues](#reporting-issues)

## Before you begin

- **Python 3.10 or newer** is required. LogLens uses only the Python standard library, so you do **not** need `pip` or third-party packages.
- **No network connection is required** once you have the files. LogLens runs locally on your computer and does **not** upload, transmit, or store your data externally.
- **Read-only:** LogLens only reads your CSV file; it does not repair, rewrite, or otherwise modify it.

> **Note on Python launchers:** The commands below use `python`. On some computers, the Python launcher is `python3` or `py` instead. Use whichever one starts Python 3.10 or newer on your computer.

## Getting the files

LogLens does not require a `pip install` or separate installation step.

1. On this repository's GitHub page, select **Code**, then **Download ZIP**.
2. Extract the ZIP archive to a folder on your computer.
3. Open a terminal and navigate to the **repository root**—the extracted folder that contains `loglens.py`:

   ```bash
   cd path/to/extracted-folder
   ```

## Verifying your setup

From the repository root, test LogLens using the included sample file (`data/sample_logs.csv`):

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```

If everything is set up correctly, you will see:

```text
Records matching ERROR: 2
```

To confirm the available command-line options at any time, run:

```bash
python loglens.py --help
```

Once your setup is working, see [Usage](../README.md#usage) for additional examples and [Input format](../README.md#input-format) before running LogLens on your own CSV files.

## Troubleshooting

If LogLens does not run as expected, check the items below:

| Area | What to check |
| :--- | :--- |
| **Python launcher** | If `python` does not work on your computer, try `python3` or `py` instead. |
| **Python version** | Confirm you are running **Python 3.10 or newer**. |
| **Working directory** | Confirm your terminal is in the **repository root** (the folder containing `loglens.py`). |
| **File path** | Confirm you included the required `--file` argument and that the path to your CSV file is spelled correctly. |
| **CSV format** | Confirm your file matches the [Input format](../README.md#input-format) (`timestamp`, `level`, and `message` headers, with uppercase `INFO`, `WARN`, or `ERROR` values). |

## Reporting issues

If the checks above do not resolve the issue, follow the steps in [Getting help](../README.md#getting-help) to open an issue in this repository.

> **Protect sensitive data:** Do not post private or sensitive log data in a public issue. Never attach an original work or personal CSV file; instead, describe the problem and include a small, sanitized example with any sensitive values removed.