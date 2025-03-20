# Linux Command Lab - File and Permission Management

## Task 1: Using the `tee` Command

### Description
The `tee` command reads from the standard input and writes to both the screen and a file.

### Steps:
1. Validate the current directory:
   ```bash
   pwd
   ```
2. Use `tee` to display the hostname and save it to `file1.txt`:
   ```bash
   hostname | tee file1.txt
   ```
3. Confirm that `file1.txt` has been created:
   ```bash
   ls
   ```

---

## Task 2: Using `sort` and `grep` Commands

### Description
The `sort` command arranges lines in a file in order, and `grep` searches for specific content.

### Steps:
1. Validate the current directory:
   ```bash
   pwd
   ```
2. Create a `test.csv` file and add data:
   ```bash
   cat > test.csv << EOF
   Factory, 1, Paris
   Store, 2, Dubai
   Factory, 3, Brasilia
   Store, 4, Algiers
   Factory, 5, Tokyo
   EOF
   ```
3. Verify the file is created:
   ```bash
   ls
   ```
4. Sort the file contents:
   ```bash
   sort test.csv
   ```
5. Search for `Paris` in the file:
   ```bash
   grep Paris test.csv
   ```

---

## Task 3: Using the `cut` Command

### Description
The `cut` command extracts sections of each line in a file.

### Steps:
1. Validate the current directory:
   ```bash
   pwd
   ```
2. Create a `cities.csv` file:
   ```bash
   cat > cities.csv << EOF
   Dallas, Texas
   Seattle, Washington
   Los Angeles, California
   Atlanta, Georgia
   New York, New York
   EOF
   ```
3. Extract only city names using `cut`:
   ```bash
   cut -d ',' -f 1 cities.csv
   ```

---

## Task 4: Using the `sed` Command

### Description
The `sed` command is used to replace text in files.

### Steps:
1. Replace the first comma (`,`) with a period (`.`) in `cities.csv`:
   ```bash
   sed 's/,/./' cities.csv
   ```
2. Replace the first comma in `test.csv`:
   ```bash
   sed 's/,/./' test.csv
   ```

---

### Summary
This exercise covered:
- Using `tee` to display and save output.
- Sorting and searching data with `sort` and `grep`.
- Extracting parts of a file using `cut`.
- Modifying file contents using `sed`.

These commands are essential for text processing and file management in Linux environments.

