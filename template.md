# URN:MRN:FIN:<NID>:
<!--ADD: Date updated-->
Updated: <YYYY-MM-DD>

## 1. Purpose and Scope

<!--ADD: definitions of the namespace-->
This specification defines the subnamespace  
```
urn:mrn:fin:<NID><NSS>:
```
for use in identifying XXX.

- **Scope:** Persistent, globally unique identifiers for all XXX.  
- **Out of scope:** 

---

## 2. Authority
<!--ADD: owner and point of contact-->
- **Namespace owner:** XXX  
- **Contact:** XXX
- **Change control:** The namespace owner maintains this specificaton, including changes and rules for assigning identifiers.

---

## 3. Namespace Structure


**General form:**

```
<!--ADD: general form description-->
urn:mrn:fin:navwarn:<NID>:<NSS>
```

**Segments:**
<!--ADD: definition of the segments (components)-->

- `<NID>` - ##DEFINITION_NID##  
- `<NSS>` - ##DEFINITION_NSS##

---

## 4. Syntax Definition

<!--ADD: ABNF definition of the namespace-->

**ABNF:**
```
SUB-MRN = "urn:mrn:fin:" NID ":" NSS

;Namespace ID (NID)
NID = alphanum *(31*(alphanum / "-") alphanum)
       ; 1-32 characters, alphanumeric or hyphen
       ; Must start and end with alphanumeric

; Namespace String (NSS)
NSS = pchar *(pchar / "/")
      ; May contain colons (":") to form sub-components
      ; Despite allowing colon, only explicitly defined sub-namespaces are allowed 

; Supporting definitions
alphanum    = ALPHA / DIGIT
pchar       = unreserved / pct-encoded / sub-delims / ":" / "@"
unreserved  = ALPHA / DIGIT / "-" / "." / "_" / "~"
pct-encoded = "%" HEXDIG HEXDIG
sub-delims  = "!" / "$" / "&" / "'" / "(" / ")" / "*" / "+" / "," / ";" / "="
ALPHA       = %x41-5A / %x61-7A   ; A-Z / a-z
DIGIT       = %x30-39             ; 0-9
HEXDIG      = DIGIT / "A" / "B" / "C" / "D" / "E" / "F" 
                    / "a" / "b" / "c" / "d" / "e" / "f"
```

## 5. Assignment & Uniqueness

<!--ADD: data to replace XXX-->

- **Assignement:** Identifiers are assigned by XXX
- **Issuing authority:**  XXX 
- **Uniqueness rule:** XXX  
- **Persistence:** Identifiers are never reassigned.

---

## 6. Lifecycle

- **Persistence:** URNs remain valid indefinitely.
---

## 7. Resolution
<!--ADD: resolution data-->
- Resolution is not implemented.
---

## 8. Syntax & Comparison Rules

- Identifiers are case-insensitive
---

## 9. Examples
<!--ADD: examples-->

```
```
---

## 10. Security and Privacy

---

## 11. Change Control

- This specification is maintained by the namespace owner 
- Historical URNs remain valid forever.

---

## 12. References

- https://fiho.fi/mrn

<!--ADD: additiona references-->
