                                       ## Unix Commands Cheat Sheet ##

## File Viewing
- `cat file.txt` — show entire file
- `head -n 5 file.txt` — first 5 lines
- `tail -n 5 file.txt` — last 5 lines
- `less file.txt` — scroll through file (q to quit)

## Searching
- `grep "pattern" file.txt` — find lines containing pattern
- `grep "^ATG" file.txt` — lines starting with ATG (^ = start of line)
- `grep -v "pattern" file.txt` — lines NOT containing pattern (-v = invert)
- `grep -c "pattern" file.txt` — count matching lines

## Pipes and Redirection
- `command1 | command2` — pipe output of command1 into command2
- `command > file.txt` — save output to file (overwrites)
- `command >> file.txt` — append output to file

## Sorting and Counting
- `sort file.txt` — sort lines alphabetically
- `sort -n file.txt` — sort numerically
- `sort -r file.txt` — reverse order
- `sort -nr file.txt` — sort numerically, highest first
- `uniq file.txt` — remove duplicate adjacent lines (use after sort!)
- `uniq -c file.txt` — count occurrences of each line
- `wc -l file.txt` — count lines

## Extracting Columns
- `cut -d' ' -f2 file.txt` — extract field 2 (space-delimited)
- `cut -d',' -f1,3 file.csv` — extract fields 1 and 3 (comma-delimited)
- `cut -d$'\t' -f2 file.tsv` — extract field 2 (tab-delimited)

## Common Combinations (the ones I use constantly)
- `grep "cancer" genes.txt | wc -l` — count cancer genes
- `sort file.txt | uniq` — get unique lines
- `cut -d' ' -f2 data.txt | sort | uniq -c` — count unique values in column 2
- `grep -v "^@" reads.txt | sort | uniq -c` — count duplicate sequences in FASTQ
- `sort file.txt | uniq -c | sort -nr | head -5` — top 5 most frequent lines