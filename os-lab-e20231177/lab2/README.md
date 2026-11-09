# Lab 2 — Linux Navigation and File Management: Individual Report

- **Student name/ID:** Nhean Sonita / e20231177
- **Ubuntu username:** `gic-nhean-sonita`
- **My values:** file1 = `tax summary.txt`, file2 = `cash flow.txt`, owner = `Sales`, reader = `HR`, third = `Engineering`
- **Files:** `evidence/paths.txt`, `evidence/tree.txt`, `evidence/checkpoint.txt`

## What I Did

| Step | My command | Current folder when I ran it |
|---|---|---|
| Move the first file (relative destination) | `mv -- "tax summary.txt" ../reports/` | `lab2/incoming/` |
| Move the second file (absolute paths) | `mv -- "/home/gic-nhean-sonita/oslab-work/lab2/incoming/cash flow.txt" "/home/gic-nhean-sonita/oslab-work/lab2/reports/"` | `lab2/` |
| Read the report from my reader department (relative path) | `cat "../Sales/tax summary.txt"` | `lab2/TechCorp/HR/` |
| The path error I made on purpose, and its message | `cat "reports/tax summary.txt"` — `No such file or directory` | `lab2/TechCorp/HR/` |
| The relative path that fixed it | `../../reports/tax summary.txt` | `lab2/TechCorp/HR/` |

## Explanation

A correct file name can still give "No such file or directory" if the path starts from the wrong current directory. A relative path depends on where I am, while an absolute path starts from the root directory. I used `mv` to move the two reports from `incoming` to `reports`. I used `cp` to copy the reports into `TechCorp/Sales` while keeping the originals in `reports`.

## What My Tests Do Not Prove

`ls` shows that files exist and where they are located, but it does not prove that their contents are identical. `cmp` compares the contents of two files and prints nothing when they are identical.

## Plus / Challenge (only if you did them)



## AI Note (optional)

