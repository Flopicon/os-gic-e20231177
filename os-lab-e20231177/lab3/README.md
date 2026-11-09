# Lab 3 — Wildcards, Hard Links and Symbolic Links: individual report

- **Student name/ID:** Nhean Sonita / e20231177
- **Ubuntu username:** gic-nhean-sonita
- **My values (`oslab values lab3`):** name = maple, tag = draft, v1 = 363, v2 = 414
- **Files:** `evidence/wildcards.txt`, `evidence/links.txt`, `evidence/replacement.txt`, `evidence/checkpoint.txt`

## What I Saw

| State | What `cat` printed for the hard link | What `cat` printed for the symbolic link | What `readlink` printed |
|---|---|---|---|
| Before the rename | `version 363` | `version 363` | `maple.txt` |
| After the rename, before the repair | `version 363` | Error: No such file or directory | `maple.txt` |
| After a new file took the old name | `version 363` | `version 414` | `maple.txt` |
| After my repair | `version 363` | `version 363` | `maple-draft.txt` |

**My repair (the two commands I wrote):**

```bash
rm -- "$name-soft.txt"
ln -s "$name-$tag.txt" "$name-soft.txt"
```

## Explanation

The symbolic link stores the filename `maple.txt`, so after the original file was renamed, the link could not find its target. When a new file named `maple.txt` was created, the symbolic link started reading that new file and printed `version 414`. The hard link still pointed to the original inode, so it continued to print `version 363`. In my output, the original file had inode `19005844`, while the replacement file had inode `19005860`. This shows that the two files had different inodes.

## What My Tests Do Not Prove

The `cat` command shows the file contents, but it does not prove whether two filenames refer to the same inode. The `ls -li` command shows inode numbers and link counts, which helps prove whether files share the same inode.

## Plus / Challenge



## AI Note

