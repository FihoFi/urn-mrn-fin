# URN:MRN:FIN:NAVWARN:
Updated: 2025-09-10

## 1. Purpose and Scope

This specification defines the subnamespace  
```
urn:mrn:fin:navwarn:
```
for use in identifying Finnish Navigational Warnings.

- **Scope:** Persistent, globally unique identifiers for all official Finnish Navigational Warnings  
- **Out of scope:** Informal or third-party notices.

---

## 2. Authority

- **Namespace owner:** Finnish Transport and Communications Agency, TRAFICOM  
- **Contact:** stefan.engstrom@traficom.fi / mikko.hovi@traficom.fi 
- **Change control:** The namespace owner maintains this specificaton, including changes and and the assignment rules.

---

## 3. Namespace Structure

**General form:**

```
urn:mrn:fin:navwarn:<producer>:<series>:<year>:<number>
```

**Segments:**

- `<producer>` — the S-62 producer code of the producer (FI00 for Traficom).  
- `<series>` — a code defining the series of a Navigational Warning
- `<year>` — four-digit Gregorian year (`YYYY`).  
- `<number>` — sequential number within the series and year

---

## 4. Syntax Definition

**ABNF:**
```
fi-navwarn = "urn:mrn:fin:navwarn:" producer ":" series ":" year ":" number
producer   = "FI00"
series     = 1*(ALPHA / DIGIT / "-")
year       = 4DIGIT
number     = 1*DIGIT
```

**Regex:**
```
^urn:mrn:fin:navwarn:FI00:([A-Za-z0-9-]+):([0-9]{4}):([0-9]+)$
```

---

## 5. Assignment & Uniqueness

- **Assignement:** Identifiers are assigned by the producer on publication of a Navigational Warning.
- **Issuing authority:** Only the producer may assign identifiers.  
- **Uniqueness rule:** Each `(series, year, number)` tuple MUST be unique.  
- **Persistence:** Identifiers are never reassigned.

---

## 6. Lifecycle
<!--
- **States:** `active`, `superseded`, `cancelled`, `expired`.  
- **Supersession:** Indicated in metadata, not by altering the URN.  
-->
- **Persistence:** URNs remain valid indefinitely.

---

## 7. Resolution

NA
<!--
URNs may be mapped to HTTP resources using this template:

```
https://navwarn.fi/urn/FI00/{series}/{year}/{number}
```

The endpoint SHOULD provide both machine-readable (JSON) and human-readable (HTML) metadata, e.g.:

- Title / short description  
- Issue date & time  
- Text of the warning  
- Status (active / cancelled / superseded)  
- Supersession links (if applicable)
-->
---

## 8. Syntax & Comparison Rules

- Identifiers are case-insensitive

---

## 9. Examples

```
urn:mrn:fin:navwarn:FI00:LF:2025:17
urn:mrn:fin:navwarn:FI00:VV:2025:42
urn:mrn:fin:navwarn:FI00:LF:2025:18
```

---

## 10. Security and Privacy

NA
<!--
- Identifiers themselves contain no personal data.  
- Resolution services should use HTTPS.  
- Optional signing of metadata is recommended for authenticity.
-->
---

## 11. Change Control

- This specification is maintained by the namespace owner 
- Historical URNs remain valid forever.

---

## 12. References

- [RFC 8141: Uniform Resource Names (URNs)](https://www.rfc-editor.org/rfc/rfc8141)  
- [IANA URN Namespaces Registry](https://www.iana.org/assignments/urn-namespaces/)  
- [IALA MRN Guidelines](https://www.iala-aism.org/)  
