# PHP Encryptor / Obfuscator — Documentation
a simple html php obfuscator tool perfect for shell using python

**Made by jrmph13**

---

## Installation

```bash
git clone https://github.com/jrmph13/html-php-obfucator-tool.git
cd html-php-obfucator-tool
```

---

## Requirements

- Python 3.6+
- PHP server (to run the output `.php` files)
- No pip installs needed

---

## How to Use

### CLI

```bash
python3 run.py <input> [options]
```

**Examples:**

```bash
# HTML to encrypted PHP (default level 3)
python3 run.py index.html -output index_encrypted.php

# HTML to encrypted PHP, level 4
python3 run.py index.html -output index_encrypted.php -level 4

# HTML to encrypted PHP, level 4 + custom mode
python3 run.py index.html -output index_encrypted.php -level 4 --custom

# HTML to encrypted PHP, compat mode (for php-wasm / shared hosting)
python3 run.py index.html -output index_encrypted.php -level 4 --compat

# PHP to encrypted PHP
python3 run.py myfile.php -output myfile_encrypted.php -level 4

# Launch web UI in browser
python3 run.py --web

# Show help
python3 run.py
```

### Web UI

```bash
python3 run.py --web
```

Opens a browser — paste your HTML or PHP, choose mode and level, download the output.

---

## Options

| Option | Default | Description |
|---|---|---|
| `input` | *(required)* | Input file — `.html` or `.php` |
| `-output FILE` | *(required)* | Output file path |
| `-level {1,2,3,4}` | `3` | Obfuscation level |
| `--custom` | off | Custom cipher mode |
| `--compat` | off | No gzip — for php-wasm / shared hosting |
| `--web` | off | Launch web UI |

---

## Levels

| Level | Description |
|---|---|
| 1 | Basic |
| 2 | Medium |
| 3 | High *(default)* |
| 4 | Maximum |

---

## Modes

| Mode | When to Use |
|---|---|
| *(no flag)* | Standard — works on all normal PHP servers |
| `--custom` | Stronger obfuscation, includes extra junk/decoy code |
| `--compat` | For php-wasm, shared hosting, or if gzip causes errors |

---

## Recommended

For maximum protection on an HTML file:

```bash
python3 run.py yourpage.html -output yourpage.php -level 4 --custom
```

---

## Troubleshooting

| Problem | Fix |
|---|---|
| `python` not found | Use `python3` instead |
| HTTP 500 error | Make sure server is PHP 7.0+ |
| Blank page | Try `--compat` mode |
| Output file too large | Use standard mode without `--custom` |
| php-wasm not working | Always add `--compat` flag |

---

*PHP Encryptor / Obfuscator — made by jrmph13*
