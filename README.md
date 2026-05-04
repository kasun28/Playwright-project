# Assignment 1 – Singlish to Sinhala Transliteration Accuracy Testing
**IT3040 – ITPM | BSc (Hons) in Information Technology | Year 3**

This project automates test cases for the Chat Sinhala transliteration function at  
[https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

---

## Project Structure

```
test_automation/
├── test_automation.py          # Main Playwright automation script
├── Assignment 1 - Test cases.xlsx   # Test case Excel file (fill TC ID, Input, Expected output)
├── Commands.txt                # Quick reference commands
└── README.md                   # This file
```

---

## Prerequisites

- Python **3.11** or **3.12** — [Download here](https://www.python.org/downloads/)
- Google Chrome (recommended) — [Download here](https://www.google.com/chrome/)

---

## Setup Instructions

### Step 1 — Clone or Download the Repository

```bash
git clone https://github.com/kasun28/Playwright-project
```

Or download the ZIP and extract it to your `D:` drive so the path is:
```
D:\test_automation\
```

### Step 2 — Open Command Prompt and Navigate to the Folder

```bash
cd /d D:\test_automation
```

### Step 3 — Install Dependencies (one-time only)

Run each command one by one:

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## How to Run the Tests

### Step 4 — Fill in the Excel File

Open `Assignment 1 - Test cases.xlsx` and ensure the following columns are filled:
- `TC ID` — e.g., `Neg_0001`
- `Input length type` — `S`, `M`, or `L`
- `Input` — the Singlish test input
- `Expected output` — the correct Sinhala translation

**Do NOT fill** `Actual output` or `Status` — the script fills these automatically.

### Step 5 — Run the Automation Script

```bash
python test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" 
```

### Step 6 — Check Results

Reopen the Excel file. The `Actual output` and `Status` columns will be filled automatically.

---

## Command Reference

| Argument | Default | Description |
|---|---|---|
| `--excel` | *(required)* | Path to the Excel file |
| `--url` | *(required)* | URL of the chat translator |
| `--wait-ms` | `5000` | Wait time (ms) after submitting input |
| `--type-delay-ms` | `80` | Delay (ms) between each keystroke |
| `--slow-mo-ms` | `200` | Slow motion delay (ms) for browser |
| `--save-every` | `1` | Save Excel after every N test cases |
| `--keep-open` | off | Keep browser open after tests finish |

---

## Test Case Coverage

This project includes **50 negative test cases** (where the system fails to produce correct output),  
covering all **24 Singlish input types** specified in Appendix 1 of the assignment:

| # | Input Type | Test Cases |
|---|---|---|
| 1 | Question forms | Neg_0001, Neg_0002 |
| 2 | Command forms | Neg_0003, Neg_0004 |
| 3 | Greetings | Neg_0005, Neg_0006 |
| 4 | Requests | Neg_0007, Neg_0008 |
| 5 | Responses | Neg_0009, Neg_0010 |
| 6 | Repeated Words | Neg_0011, Neg_0012 |
| 7 | Inputs with Punctuation Marks | Neg_0013, Neg_0014 |
| 8 | Romanization / Spelling Variants | Neg_0015, Neg_0016 |
| 9 | Isolated English Word Insertions | Neg_0017, Neg_0018 |
| 10 | Multi-Word English Phrases | Neg_0019, Neg_0020 |
| 11 | English Digital Terms | Neg_0021, Neg_0022 |
| 12 | Platform/App Names | Neg_0023, Neg_0024 |
| 13 | English Abbreviations/Acronyms | Neg_0025, Neg_0026 |
| 14 | English Clipped Forms | Neg_0027, Neg_0028 |
| 15 | Place Names Embedded | Neg_0029, Neg_0030 |
| 16 | Person Names Embedded | Neg_0031, Neg_0032 |
| 17 | Inputs with Numbers/Numeric Suffixes | Neg_0033, Neg_0034 |
| 18 | Inputs with Currency | Neg_0035, Neg_0036 |
| 19 | Inputs with Time Formats | Neg_0037, Neg_0038 |
| 20 | Inputs with Dates | Neg_0039, Neg_0040 |
| 21 | Inputs with Unit of Measurements | Neg_0041, Neg_0042 |
| 22 | Inputs with Slang and Casual Phrasing | Neg_0043, Neg_0044, Neg_0050 |
| 23 | Online Identifiers | Neg_0045, Neg_0046 |
| 24 | Inputs Containing Emojis | Neg_0047, Neg_0048 |
| — | Additional (free choice) | Neg_0049, Neg_0050 |

---

## Notes

- Only the **Chat Sinhala** transliteration function is tested — Standard Sinhala is out of scope.
- All test case IDs begin with `Neg` as these are negative test cases.
- Input length types: **S** (≤ 30 chars), **M** (31–299 chars), **L** (300–450 chars).
