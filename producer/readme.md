# URN:MRN:FIN:<NID>:
<!--ADD: Date updated-->
Updated: 2025-11-05

## 1. Purpose and Scope

<!--ADD: definitions of the namespace-->
This specification defines the subnamespace  
```
urn:mrn:fin:producer:
```
for use in identifying any resources assigned and further specified by a (Finnish) producer of S-100 products.

- **Scope:** Persistent, globally unique identifiers for all resources assigned by the specific S-100 producer, for use in S-100 products.  
- **Out of scope:** Resource names not intended for use within S-100 products, or given to other aspects of the same resources, by other stakeholders using other namespaces. 

---

## 2. Authority
<!--ADD: owner and point of contact-->
- **Namespace owner:** Finnish Transport and Communications Agency, TRAFICOM
- **Contact:** stefan.engstrom@traficom.fi / mikko.hovi@traficom.fi
- **Change control:** The namespace owner maintains this specificaton, including changes and rules for assigning identifiers.

### Assignment of sub-namespaces to IHO Producer Code owners
Each (Finnish) owner of a valid producer code within the IHO S-62 Producer Code register is automatically the owner of the corresponding namespace within the namespace urn:mrn:fin:producer:<PCODE>. Anyway, due to the requirement for provision of documentation of all MRN-namsespaces, **a Producer Specific Namespace cannot be used until the specified documentation is added to urn:mrn:fin documentation** in https://fiho.fi/mrn.

A producer code owner, shall provide an explicit specification of the requested namespace, using the [markdown specification template](https://github.com/FihoFi/urn-mrn-fin/blob/main/template.md?plain=1), and sending it by email to above points of contact. Once validated and established, the specificaiton of a new sub-namespace will be added as an explicit definition within a subfolder to this repository.

---

## 3. Namespace Structure


**General form:**
<!--ADD: general form description-->
```
urn:mrn:fin:producer:<PCODE>:<PSS>
```

**Segments:**
<!--ADD: definition of the segments (components)-->

- `<PCODE>` - The S-100 producer code (alpha) of a producer in the IHO Producer Code Register (S-62).  
- `<PSS>` - The Producer Specific Namespace, as defined and documented by the producer.

---

## 4. Syntax Definition

<!--ADD: ABNF definition of the namespace-->

**ABNF:**
```
SUB-MRN = "urn:mrn:fin:producer" PCODE ":" PSS

;Producer code (PCODE)
PCODE = 4alphanum
       ; exactly 4 alphanumeric characters
       
;Producer Specific Namespace String (PSS)
PSS = pchar *(pchar / "/")
      ; May contain colons (":") to form sub-components
      ; Despite allowing colon, only explicitly defined sub-namespaces are allowed
      ; Each producer must provide additional documentation to define the sub-namespaces allowed within the PSS  

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

- **Assignement:** Identifiers (PCODE) are assigned by the namespce owner, based on a request by the owner of a valid producer code within the IHO S-62 Producer Code register. Documentation of the Producer Specific Namespace must follow the specifications set for this namesapace and any specifications inherited from parent namesapaces as defined in URN or MRN specifications.  
- **Issuing authority:** The Finnish Transport and Communications Agency, TRAFICOM
- **Uniqueness rule:** According to rules set by IHO for use in the S-62 Producer Code register
- **Persistence:** According to IHO S-62 Producer Code register

>[!NOTE]
>Each (Finnish) owner of a valid producer code within the IHO S-62 Producer Code register is automatically the owner of the corresponding namespace within the namespace urn:mrn:fin:producer:<PCODE>. Anyway, due to the requirement for provision of documentation of all MRN-namsespaces, a Producer Specific Namespace cannot be used until specific documentation is provided and added to urn:mrn:fin:producer documentation in https://fiho.fi/mrn.
**Check Part 2 in this document for further guidance.**
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
