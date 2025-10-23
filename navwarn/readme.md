# URN:MRN:FIN:NAVWARN:
Updated: 2025-10-23

## 1. Purpose and Scope

This specification defines the sub-namespace  
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

- `<producer>` — the IHO S-62 / S-100  producer code of the producer (FI01 for Turku Radio / Traficom).  
- `<series>` — a code defining the series of a Navigational Warning
- `<year>` — four-digit Gregorian year (`YYYY`).  
- `<number>` — sequential number within the series and year. Number formatting including the use of leading zeroes must be consistent within the parent namespace (year).

>[!NOTE]
>The resource name is formed by providing all defined components, separated by colon. Currently only one producer (FI01) is recognized. Each series must be defined by at least one character or digit, and the year provided using four digits (2025, 2026 etc.). The number may contain only digits.
---

## 4. Syntax Definition

**ABNF:**
```
fi-navwarn = "urn:mrn:fin:navwarn:" producer ":" series ":" year ":" number
producer   = "FI01"
series     = 1*(ALPHA / DIGIT / "-")
year       = 4DIGIT
number     = 1*DIGIT
```

**Regex:**
```
^urn:mrn:fin:navwarn:FI01:([A-Za-z0-9-]+):([0-9]{4}):([0-9]+)$
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
https://navwarn.fi/urn/FI01/{series}/{year}/{number}
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
urn:mrn:fin:navwarn:FI01:LC:2025:17
urn:mrn:fin:navwarn:FI01:VV:2025:42
urn:mrn:fin:navwarn:FI01:LC:2025:18
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

- https://github.com/FihoFi/urn-mrn-fin/
