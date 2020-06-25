# GREP - Global Regular Expression Print

Searches a file for a particular pattern of characters, and displays all lines that contain that expression.

The pattern is known as regular expressions (or Regex).

## Syntax

```bash
$ grep [options] pattern [files]
```

## List of Options

-c : This prints only a count of the lines that match a pattern
-h : Display the matched lines, but do not display the filenames.
-i : Ignores, case for matching
-l : Displays list of a filenames only.
-n : Display the matched lines and their line numbers.
-v : This prints out all the lines that do not matches the pattern
-e exp : Specifies expression with this option. Can use multiple times.
-f file : Takes patterns from file, one per line.
-E : Treats pattern as an extended regular expression (ERE)
-w : Match whole word
-o : Print only the matched parts of a matching line,
 with each such part on a separate output line.
 ^pattern: Will only match the pattern if it is at the beginning of the line.
 pattern$: Will only match the pattern if it is at the end of the line.

## Special Characters Examples

- \ - Backslash or escape character which is used to give the other characters their special functions.

- {} - These are used to as a range quantifier. ie. "b{3,4}" will match 'bbb' or 'bbbb'

- [] - Looks to match a single character within the range inside. ie. "[a-d]" will looks for matches for "a", "b", "c" or "d"
    - the ^ character when used as the first character inside [^a-d] looks for anything that is not in that range.

- () - Groups characters (or other regexes) ie. "(ab)\1" matches "abab"

- * - Match 0 or more quantifier

- + - Match 1 or more quantifier

- | - Matches alternatives (or function)


## BRE (basic regex) vs ERE (extended regex)

- Special Characters in Basic Regex must be prefixed by a '\' in order to work as a intended (they will just be considered as part of the pattern without it)

- In Extended Regex however, special characters work by default unless prefixed with a '\'

## Examples of GREP in use

For this example we will use the "fruits.txt" file.

In bash:

1. Count number of times 'Strawberry' is in the file
```bash
$ grep -c "Strawberry" fruits.text

--> 1
```
2. Print out every instance of "pom" appears in file
```bash
$ grep -i "pom" fruits.txt

-->
Pomegranate
Pomelo
Pomegranate
Pomelo
Pomegranate
Pomelo

```

3. Print out lines and line number of every match with 'can' (case ignored) - Example of using more than one command together.
And then write to a new .txt file named 'matched fruits' (using the > operator. This creates or overwrites the file. Use >> to append to existing file)

```bash
$ grep -i -n "can" fruits.txt > matched_fruits.txt

$ cat matched_fruits.txt

--> 117:Cantaloupe
```

4. Print out lines that contain "berry" or "fruit" (ignoring case on both) and append to matched_fruits.txt

```bash
$ grep -i -e "berry" -i -e "fruit" fruits.txt >> matched_fruits.txt

$ cat matched_fruits.txt to see output
```
