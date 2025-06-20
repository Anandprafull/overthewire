<!-- ssh -p 2220 bandit(n)@bandit.labs.overthewire.org

ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If bandit1
263JGJPfgU6LtdEvgfWU1XP5yac29mFx bandit2
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx bandit3   cat spaces\ in\ this\ filename
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ bandit4   cat ./...Hiding-From-You
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw bandit5   file ./-*
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG bandit6   find -type f -size 1033c
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj bandit7   cat /var/lib/dpkg/info/bandit7.password
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc bandit8   awk '/^millionth/ {print $2;}' data.txt
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM bandit9   cat data.txt | sort | uniq -u
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey bandit10  strings data.txt | grep "="
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr bandit11  base64 --decode data.txt
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4 bandit12  cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn bandit13  tmpdir=$(mktemp -d) && cd "$tmpdir" && cp 						   ~/data.txt . && xxd -r data.txt data && 						   while :; do ft=$(file data); case "$ft" in 						   *gzip*) mv data data.gz && gunzip data.gz ;; 					  *bzip2*) mv data data.bz2 && bunzip2 data.bz2 ;; 					  *tar*) mv data data.tar && tar -xf data.tar && 					  rm data.tar ;; *ASCII*) cat data && break ;; *) 					  echo "Unknown format: $ft"; break ;; esac; file 					  data; done
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS bandit14 ssh -i sshkey.private bandit14@localhost -p 2220
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo bandit15 cat /etc/bandit_pass/bandit14 | nc localhost 30000 -->

# OverTheWire: Bandit Solutions (as of June 2025)

So I've started doing something for timepass after internals exams and this is it :>

Interactively solve Bandit levels on OverTheWire.  
Replace `<n>` with the appropriate level number (e.g., bandit0).  
All commands assume the default port **2220**.

---

## How to Connect

```bash
ssh -p 2220 bandit<n>@bandit.labs.overthewire.org
```

---

## Solutions by Level

### bandit1

**Password:**  
```
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

---

### bandit2

**Password:**  
```
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---

### bandit3 – File with Spaces

**Password:**  
```
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

**Command to read the password file:**
```bash
cat spaces\ in\ this\ filename
```

---

### bandit4 – Hidden File

**Password:**  
```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

**Command to read the password file:**
```bash
cat ./...Hiding-From-You
```

---

### bandit5 – File with Dash

**Password:**  
```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

**Command to identify and read the file:**
```bash
file ./-*
```

---

### bandit6 – Find by Size

**Password:**  
```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

**Find and read the file with size 1033 bytes:**
```bash
find . -type f -size 1033c
```

---

### bandit7 – Direct File Path

**Password:**  
```
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

**Read the password:**
```bash
cat /var/lib/dpkg/info/bandit7.password
```

---

### bandit8 – AWK Filtering

**Password:**  
```
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

**Use AWK to extract the password:**
```bash
awk '/^millionth/ {print $2;}' data.txt
```

---

### bandit9 – Unique Line

**Password:**  
```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

**Find the unique password:**
```bash
cat data.txt | sort | uniq -u
```

---

### bandit10 – Strings and Grep

**Password:**  
```
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

**Find the password with:**
```bash
strings data.txt | grep "="
```

---

### bandit11 – Base64 decode

**Password:**  
```
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

**Decode the file:**
```bash
base64 --decode data.txt
```

---

### bandit12 – ROT13 Cipher

**Password:**  
```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

**Decode with tr:**
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

---

### bandit13 – Multiple Archive Formats

**Password:**  
```
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

**Script to extract recursively:**
```bash
tmpdir=$(mktemp -d) && cd "$tmpdir" && cp ~/data.txt . && xxd -r data.txt data && \
while :; do
  ft=$(file data)
  case "$ft" in
    *gzip*) mv data data.gz && gunzip data.gz ;;
    *bzip2*) mv data data.bz2 && bunzip2 data.bz2 ;;
    *tar*) mv data data.tar && tar -xf data.tar && rm data.tar ;;
    *ASCII*) cat data && break ;;
    *) echo "Unknown format: $ft"; break ;;
  esac
  file data
done
```

---

### bandit14 – SSH Private Key

**Password:**  
```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

**SSH using a private key:**
```bash
ssh -i sshkey.private bandit14@localhost -p 2220
```

---

### bandit15 – Netcat

**Password:**  
```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

**Send previous password via netcat:**
```bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```

---

Feel free to copy and expand this README as you progress through the levels!  
Happy hacking!
