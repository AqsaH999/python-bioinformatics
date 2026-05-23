                                              ## Unix - Week 1 Learning Log##

## What I Learned This Week

This week I learned basic Unix commands for viewing, searching, and manipulating text files — the foundation of bioinformatics data processing.

### Commands Mastered
- **grep**: Search for patterns in files. The `^` symbol means "start of line" (e.g., `grep "^@"` finds FASTQ read IDs)
- **pipes (|)**: Chain commands together. Output of one command becomes input to the next
- **sort**: Arrange lines alphabetically or numerically (`-n` for numbers, `-r` for reverse)
- **uniq**: Remove duplicates (only works on adjacent lines, so always use after `sort`)
- **cut**: Extract specific columns from delimited files (`-d' '` for space, `-f2` for field 2)
- **wc -l**: Count lines in a file

### Real Bioinformatics Applications
- Counted how many reads are in a FASTQ file: `grep "^@" reads.txt | wc -l`
- Found duplicate sequences and their frequencies: `grep -v "^@" reads.txt | sort | uniq -c`
- Extracted and counted unique chromosomes from a gene list: `cut -d' ' -f2 genes.txt | sort | uniq | wc -l`
- Found the most common sequence: `grep -v "^@" reads.txt | sort | uniq -c | sort -nr | head -1`

### Key Insights
- Pipes are incredibly powerful — you can build complex analyses by chaining simple commands
- `sort | uniq` is a pattern I'll use constantly (uniq only works on sorted data)
- The `-v` flag in grep (invert match) is useful for excluding header lines
- Always use `-l` (lowercase L) in `wc -l`, not `-1` (number one) — easy mistake to make

### Things I Found Tricky
- Remembering that `uniq` only removes *adjacent* duplicates — forgot to sort first and got confused
- The `^` symbol for "start of line" in grep patterns — need more practice with regex
- Distinguishing between `-1` (number) and `-l` (letter) in commands

### Next Week Goals
- Learn more grep patterns (regex basics)
- Practice combining 4+ commands in one pipeline
- Work with real FASTA/FASTQ files (not toy examples)