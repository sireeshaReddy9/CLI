# Linux Commands Reference Guide

## man

**Description:**
- Shows the manual for a given command
- Explains syntax, flags, options with examples
- Reliable source of truth

**Syntax:**
```bash
man <command>
```

**Examples:**
```bash
man ls
man chmod
```

---

## cd

**Description:**
- Change directory (folder) in the file system

**Syntax:**
```bash
cd <directory>
```

**Special Directories:**
- `cd .` - Refers to current directory
- `cd ..` - Move one level up (one folder) in the file system
- `cd ~` or `cd` - Refers to home directory
- `cd -` - Switches to previous directory

**Examples:**
```bash
cd /home/user/documents
cd ..
cd ~
cd -
```

---

## mkdir

**Description:**
- Creates a new directory (folder)

**Syntax:**
```bash
mkdir <dirname>
```

**Create Nested Directories:**
```bash
mkdir -p project/src/controllers
```
> `-p` creates parent directories automatically

**Examples:**
```bash
mkdir my_folder
mkdir -p app/src/components
```

---

## mv

**Description:**
- Move a file/directory to another folder
- Rename files/directories

**Syntax:**
```bash
mv source destination
```

**Examples:**
```bash
mv file.txt /tmp/
mv one.txt uno.txt
```

**Flags:**
- `mv -i old.txt new.txt` - Interactive (prompts before overwrite)
- `mv -v a.txt /tmp/` - Verbose (shows operation details)

---

## cp

**Description:**
- Copy a file/directory to another file/folder

**Syntax:**
```bash
cp source destination
```

**Examples:**
```bash
cp file.txt backup.txt
cp -r folder1 folder2
```

**Flags:**
- `cp -r folder1 folder2` - Recursive (copies everything inside folder)
- `cp -rp folder1 folder2` - Preserve permissions
- `cp -i file1 file2` - Interactive (asks before overwriting)
- `cp -v file1 file2` - Verbose (shows what is being copied)

---

## ls

**Description:**
- List the directory (folder)/files system

**Syntax:**
```bash
ls [options]
```

**Flags:**
- `ls -l` - Long format (permissions, owner, size)
- `ls -a` - Show hidden files (.files)
- `ls -lh` - Human-readable sizes (KB, MB)
- `ls -R` - Recursive listing
- `ls -lt` - Sort by time
- `ls -lS` - Sort by size
- `ls -lr` - Sort reverse

**Examples:**
```bash
ls -l
ls -a
ls -lh
ls -R
ls -lt
```

---

## pwd

**Description:**
- Shows current directory path

**Syntax:**
```bash
pwd
```

**Example Output:**
```bash
/home/sireesha
```

---

## rm

**Description:**
- Deletes files or directories permanently

**Syntax:**
```bash
rm file.txt
rm -r folder
```

**Flags:**
- `rm -f file.txt` - Force (no confirmation, ignores errors)
- `rm -r folder` - Recursive (delete directory and contents)
- `rm -rf delete` - Force recursive delete

**Examples:**
```bash
rm file.txt
rm -r my_folder
rm -f old_file.txt
rm -rf temp_directory
```

---

## chmod

**Description:**
- Controls who can read, write, execute a file

**Permission Types:**
- `r` → read
- `w` → write
- `x` → execute

**Users:**
- `u` → owner
- `g` → group
- `o` → others

### Numeric Permission System

| Number | Permission |
|--------|------------|
| 4 | read |
| 2 | write |
| 1 | execute |

**Example:**
```bash
chmod 755 a.txt
```
- Owner → read/write/execute (7 = 4+2+1)
- Group → read/execute (5 = 4+1)
- Others → read/execute (5 = 4+1)

### Symbolic Mode

**Syntax:**
```bash
chmod [user][operation][permission] file
```

**Examples:**
```bash
chmod u+x a.txt    # Add execute permission for owner
chmod g-w a.txt    # Remove write permission for group
chmod o+r a.txt    # Add read permission for others
```

---

## chown

**Description:**
- Change file owner and group

**Syntax:**
```bash
chown user file
chown user:group file
```

**Examples:**
```bash
sudo chown sireesha a.txt
sudo chown sireesha:developers a.txt
```

**Use Cases:**
```bash
# Change only owner
sudo chown john document.txt

# Change owner and group
sudo chown john:developers project_folder

# Change recursively for directories
sudo chown -R john:developers /var/www/html
```

---
