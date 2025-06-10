# 🐚 04 – Bash Variables, Conditionals & File Testing

Welcome to **Day 4** of your `ParrotOS Practical Guide`!  
Today, we cover foundational Bash scripting concepts: **variables, environment variables, conditionals, and file testing**.

---

## 📝 1. Variables & Environment Variables

### Defining Variables

```bash
name="Hassan"
echo "Hello, $name"
```

- No spaces around `=` when assigning variables.  
- Use `$variable` to access the variable's value.

### Environment Variables

These are predefined system variables accessible in any shell or script:

```bash
echo $USER     # Your current username
echo $HOME     # Your home directory
echo $SHELL    # Your default shell path
echo $PWD      # Current working directory
```

Use environment variables to make scripts dynamic and adaptable to different users and environments.

---

## 🤔 2. Conditionals: `if`, `else`, `elif`

### Syntax

```bash
if [ condition ]; then
  # commands if condition is true
elif [ other_condition ]; then
  # commands if other_condition is true
else
  # commands if none of the above conditions are true
fi
```

### Important Notes

- **Spaces are mandatory** after `[` and before `]`.
- Always **quote variables** in conditions: `[ "$var" = "value" ]`.
- The `then` keyword can be on the same line after a semicolon (`;`) or on the next line.

### Number Comparison Operators

| Operator | Meaning                  |
|----------|--------------------------|
| `-eq`    | equal                    |
| `-ne`    | not equal                |
| `-gt`    | greater than             |
| `-lt`    | less than                |
| `-ge`    | greater than or equal to |
| `-le`    | less than or equal to    |

### String Comparison Operators

| Operator | Meaning             |
|----------|---------------------|
| `=`      | equal               |
| `!=`     | not equal           |
| `-z`     | string is empty     |
| `-n`     | string is not empty |

---

## 🔢 Examples

### Number Check

```bash
num=5
if [ "$num" -gt 0 ]; then
  echo "Positive number"
else
  echo "Zero or negative"
fi
```

### If-Elif-Else Example

```bash
temp=25
if [ "$temp" -gt 30 ]; then
  echo "It's hot."
elif [ "$temp" -ge 20 ]; then
  echo "It's warm."
else
  echo "It's cold."
fi
```

---

## 📂 3. File Testing Operators

| Operator | Meaning               | Example                   |
|----------|-----------------------|---------------------------|
| `-e`     | File or dir exists    | `[ -e /path/to/file ]`    |
| `-f`     | Regular file exists   | `[ -f /path/to/file ]`    |
| `-d`     | Directory exists      | `[ -d /path/to/dir ]`     |
| `-r`     | File is readable      | `[ -r /path/to/file ]`    |
| `-w`     | File is writable      | `[ -w /path/to/file ]`    |

---

## 🛠 4. Practical Script Examples

### Backup Directory Check

```bash
backup_dir="$HOME/backup"

if [ ! -d "$backup_dir" ]; then
  echo "Backup directory does not exist. Creating..."
  mkdir -p "$backup_dir"
else
  echo "Backup directory already exists."
fi
```

### Simple Number Comparison

```bash
read -p "Enter the number: " num

if [ "$num" -gt 10 ]; then
  echo "The number is greater than 10"
else
  echo "The number is less than or equal to 10"
fi
```

---

## ⚠️ Common Errors & Fixes

| Issue                                 | Cause                        | Fix                                           |
|--------------------------------------|------------------------------|-----------------------------------------------|
| syntax error near unexpected token   | No spaces around `[` or `]` | Add spaces: `if [ "$num" -gt 10 ]; then`     |
| Variables not expanding or empty     | Missing `$` prefix          | Use `$num` instead of `num`                   |
| Assigning variables with spaces      | Spaces around `=`           | Use `num=5`, not `num = 5`                    |

---

## 🎯 Summary Commands

| Task                      | Command Example               |
|---------------------------|-------------------------------|
| Define variable           | `name="Hassan"`               |
| Read user input           | `read -p "Enter number: " num`|
| Number comparison         | `[ "$num" -gt 10 ]`           |
| Check if directory exists | `[ -d "$dir" ]`               |
| Create directory          | `mkdir -p "$dir"`             |

---

Keep practicing! Bash scripting will become second nature with time 🚀
