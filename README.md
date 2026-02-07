# Passgen - Personal Wordlist Generator

```

---

| || | __\ \/ / __| __/ __|
| __ | | >  <\__ \ | (

||||_//\_\_/\___|

```

**Passgen** is a Python tool created by **Max** for **educational and authorized security testing purposes**.  
It generates custom wordlists based on personal information with various transformations.  
Runs perfectly on **Termux (Android)** and all Linux terminals.

---

## ⚠️ Disclaimer

**FOR EDUCATIONAL AND AUTHORIZED TESTING ONLY**  
This tool must only be used on systems you own or have explicit permission to test.  
The author is **not responsible** for any misuse or illegal activities.

---

## 📦 Installation

### Termux (Android)
```bash
pkg update && pkg upgrade
pkg install python git
pip install rich
git clone https://github.com/max/passgen.git
cd passgen
python passgen.py
```

Linux/Mac

```bash
git clone https://github.com/max/passgen.git
cd passgen
pip install rich
python passgen.py
```

Windows

```bash
git clone https://github.com/max/passgen.git
cd passgen
pip install rich
python passgen.py
```

---

🚀 Quick Start

1. Run the tool:
   ```bash
   python passgen.py
   ```
2. Enter information when prompted:
   ```
   First name: john
   Last name: doe
   Nickname: jd (optional)
   Team: dev (optional)
   Date: 01/01/1990 (or ddmmyyyy)
   ```
3. Check generated wordlist:
   ```bash
   cat wordlist.txt
   ```

---

🎯 Features

· ✅ Case Variations (john → JOHN, John, JohnDoe)
· ✅ Leet Speak (john → j0hn, alex → 4l3x)
· ✅ Separators (-, _, ., none)
· ✅ Numeric Tails (00-99 + recent years)
· ✅ Token Combinations (name+surname+date permutations)
· ✅ Beautiful Terminal UI with Rich library
· ✅ Termux Compatible (works on Android)

---

⚙️ Configuration

Edit these variables in passgen.py:

```python
MAX_COMBO_TOKENS = 3     # Max tokens per combination (1-3)
ADD_LEET = True          # Enable leetspeak (a→4, e→3, etc.)
ADD_CASE_VARIANTS = True # Enable case variations
ADD_SEPARATORS = True    # Add -, _, . between tokens
ADD_NUM_TAILS = True     # Add numeric suffixes
MIN_LEN = 7              # Minimum password length
MAX_LEN = 24             # Maximum password length
OUTPUT_FILE = "wordlist.txt"  # Output filename
```

---

📊 Example Output

Input:

· First: john
· Last: doe
· Date: 01/01/1990

Generated samples:

```
johndoe
JohnDoe
JOHNDOE
john.doe
john-doe
j0hnD03
johndoe1990
johndoe01
J0hnD031990
... (thousands more)
```

---

🔧 Advanced Usage

Use with Hashcat

```bash
python passgen.py
hashcat -m 0 hashes.txt -a 0 wordlist.txt
```

Use with John the Ripper

```bash
john --wordlist=wordlist.txt hashfile
```

Filter results

```bash
# Get passwords 8-12 chars
grep -E '^.{8,12}$' wordlist.txt > filtered.txt
```

Merge with other wordlists

```bash
cat wordlist.txt otherlist.txt > combined.txt
sort -u combined.txt > final.txt
```

---

🐛 Troubleshooting

No colors in Termux?

```bash
export TERM=xterm-256color
export COLORTERM=truecolor
```

Rich library not installing?

```bash
pip install --upgrade pip
pip install rich
```

Python not found?

```bash
# Termux
pkg install python

# Linux
sudo apt install python3 python3-pip

# Mac
brew install python
```

---

📁 Project Structure

```
passgen/
├── passgen.py          # Main script
├── wordlist.txt        # Generated output
├── README.md           # This file
└── requirements.txt    # Python dependencies
```

---

👨‍💻 Author

Max - Security Researcher & Tool Developer

· Telegram: @maxtools
· GitHub: https://github.com/max

---

🛡️ Responsible Usage

✅ DO use for:

· Testing your own systems
· Authorized penetration tests
· CTF competitions
· Security education

❌ DO NOT use for:

· Unauthorized access
· Illegal activities
· Harassment
· Violating ToS

---

📄 License

Educational Use - For authorized security testing only.

---

⭐ If this tool helped you, please star the repository!

