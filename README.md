# Gradebook Munger

A single static page that reads a gradebook CSV export and produces:

1. **Copies to print** – how many copies of each assignment to print, based on students' missing work.
2. **Failing students** – everyone whose overall grade is below a cutoff, with their missing work.
3. **JSON / YAML download** – failing students mapped to their missing assignments.

## Privacy

Everything runs in your browser. The CSV is never uploaded to a server, and the page loads no external scripts. Do not commit gradebook exports to this repo (`*.csv` is git-ignored).

## Usage

Open `index.html` in a browser (or the GitHub Pages URL) and drop in the gradebook CSV.

Settings:
- **Failing cutoff** – overall grade below this is failing (default 60).
- **Absent** – whether `Absent` counts as missing (default on). `Exempt` and blank cells never count.
- **Categories** – which grading categories to include (default Homework and Classwork).
- **Print copies for** – all students, or failing students only.

The category and Absent settings also apply to the JSON/YAML download.

## Expected CSV format

The export needs `First Name`, `Last Name`, `Unique User ID` and `Overall` columns, plus assignment score columns named like:

```
Assignment name (Max Points: 10, Due Date: 8/24/26 11:59pm, Grading Category: Homework)
```

Assignments that share a name (e.g. `HW`) are labelled with their due date.
