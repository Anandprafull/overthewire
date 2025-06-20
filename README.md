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


OverTheWire: Bandit Solutions As of June 2025
Interactively solve Bandit levels on OverTheWire.
Replace (n) with the appropriate level (e.g., bandit0).
All commands assume the default port 2220.

How to Connect
<details> <summary><strong>SSH into Bandit</strong></summary>
bash
ssh -p 2220 bandit<n>@bandit.labs.overthewire.org
</details>
Solutions by Level
<details> <summary><strong>bandit1</strong></summary>
Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
Connect as bandit1 and use the password above.

</details> <details> <summary><strong>bandit2</strong></summary>
Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
Connect as bandit2 and use the password above.

</details> <details> <summary><strong>bandit3 – File with Spaces</strong></summary>
Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
Command to read the password file:

bash
cat spaces\ in\ this\ filename
</details> <details> <summary><strong>bandit4 – Hidden File</strong></summary>
Password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
Command to read the password file:

bash
cat ./...Hiding-From-You
</details> <details> <summary><strong>bandit5 – File with Dash</strong></summary>
Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
Command to identify and read the file:

bash
file ./-*
</details> <details> <summary><strong>bandit6 – Find by Size</strong></summary>
Password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
Find and read the file with size 1033 bytes:

bash
find . -type f -size 1033c
</details> <details> <summary><strong>bandit7 – Direct File Path</strong></summary>
Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
Read the password:

bash
cat /var/lib/dpkg/info/bandit7.password
</details> <details> <summary><strong>bandit8 – AWK Filtering</strong></summary>
Password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
Use AWK to extract the password:

bash
awk '/^millionth/ {print $2;}' data.txt
</details> <details> <summary><strong>bandit9 – Unique Line</strong></summary>
Password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
Find the unique password:

bash
cat data.txt | sort | uniq -u
</details> <details> <summary><strong>bandit10 – Strings and Grep</strong></summary>
Password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
Find the password with:

bash
strings data.txt | grep "="
</details> <details> <summary><strong>bandit11 – Base64 decode</strong></summary>
Password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
Decode the file:

bash
base64 --decode data.txt
</details> <details> <summary><strong>bandit12 – ROT13 Cipher</strong></summary>
Password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
Decode with tr:

bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
</details> <details> <summary><strong>bandit13 – Multiple Archive Formats</strong></summary>
Password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
Script to extract recursively:

bash
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
</details> <details> <summary><strong>bandit14 – SSH Private Key</strong></summary>
Password: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
SSH using a private key:

bash
ssh -i sshkey.private bandit14@localhost -p 2220
</details> <details> <summary><strong>bandit15 – Netcat</strong></summary>
Password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Send previous password via netcat:

bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
</details>
Feel free to copy and expand this README as you progress through the levels!
Happy hacking!

