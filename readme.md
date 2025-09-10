# URN:MRN:FIN
Updated: 2025-09-10

The urn:mrn:fin namespace is a national URN (Uniform Resource Name) namespace used by Finland to uniquely identify maritime resources. It forms part of the broader Maritime Resource Name (MRN) framework, supporting the needs of Finnish maritime authorities, organizations, and stakeholders.

The use of urn:mrn:fin enables:
* Unique identification of maritime entities and data
* Interoperability across systems and platforms
* Consistent management both within Finland and in global contexts

Main namespace documentation is available at: https://github.com/FihoFi/urn-mrn-fin/

## 1. Purpose and Scope

This specification defines the subnamespace  
```
urn:mrn:fin:
```
for use in identifying Finnish Maritime Resources.

- **Scope:** Persistent, globally unique identifiers for martitime resources managed- or needed by Finnish stakeholders. 

>[!NOTE]
>The **primary goal** of this namespace is to provide unique identification of maritime resources managed by Finnish stakeholders.
>
>A **secondary goal** is to additionally provide unique identifiers (within the MRN framework) for any externally established identification schemes, as needed by national stakeholders, systems, and data specifications such as e-Navigation services and IHO S-100.
>
>The secondary goal is intended as a transitional solution. Externally managed identifiers may be registered under the national namespace until an appropriate external urn:mrn namespace becomes available. In such cases, a resource may temporarily hold both a national MRN and a later authoritative MRN. 
>
>Assigning multiple identifiers to a single resource is explicitly permitted under RFC 8141, which states: “A single resource MAY have more than one URN assigned to it, either in the same URN namespace (if the URN namespace permits it) or in different URN namespaces, and for either similar purposes or different purposes.”

<!--- **Out of scope:** Informal or third-party notices.-->

---

## 2. Authority

- **Namespace owner:** Finnish Transport and Communications Agency, TRAFICOM  
- **Contact:** stefan.engstrom@traficom.fi / mikko.hovi@traficom.fi 
- **Change control:** The namespace owner maintains this specificaton, including changes and the rules for assignment of identifiers.

---

## 3. Namespace Structure

**General form:**

```
urn:mrn:fin:<OSNID>:<OSNS>
```

**Segments:**

- `<OSNID>` — Organization-Specific Namespace ID
- `<OSNS>` — Organization-Specific Namespace String

>[!NOTE]
>According to IALA guidance, OID Owners may define further sub-namespaces for representing further internal hierarchies and de-centrally organize the assignment of MRN in these subspaces.
In the URN framework, the colon character (:) is used to separate major components such as the Namespace Identifier (NID), and the Namespace Specific String (NSS). Although colons may also appear within the NSS, they do not automatically create hierarchy. Any structure within the NSS must therefore be explicitly defined in the relevant namespace specification. 

### Sub-namespaces within the Organization-Specific Namespace String
**Within urn:mrn:fin, the concept of using colon (:) to organize identifiers into hierarchical sub-namespaces is retained**. This rule applies to all sub-namespaces within urn:mrn:fin.

---

## 4. Syntax Definition

**ABNF:**
```
; General structure for all MRN (Maritime Resource Names) adopted to urn:mrn:fin
MRN = "urn:mrn:fin:" OSNID ":" OSNS

; Organization-Specific Namespace ID (OSNID)
OSNID = alphanum *(31*(alphanum / "-") alphanum)
       ; Managed by the OID owner
       ; 1–32 characters, alphanumeric or hyphen
       ; Must start and end with alphanumeric

; Organization-Specific Namespace String (OSNS)
OSNS = pchar *(pchar / "/")
      ; Managed by the OID owner
      ; May contain colons (":") to form sub-components

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

- **Assignement:** Identifiers (OSNID) are assigned by the owner of urn:mrn:fin
- **Uniqueness rule:** Each OSNID must be unique, **the use of colon within the OSNS MUST NOT lead to the formation of a sub-namespace that is not documented**.
- **Documentation:** Each OSNID, and sub-namespace must be documented within the urn:mrn:fin centarl documentation 
- **Persistence:** Identifiers are never reassigned.

>[!NOTE]
>Even though the OSNS rule allows the use of colon (:), within urn:mrn:fin this implies a sub-namespace. As each namespace must be documented and defined, the use of colon within identifiers is restricted to such cases where the generated sub-namespace is documented (See part 12 of this document, *Explicit and implicit documentation of namespaces*).

---

## 6. Lifecycle
<!--
- **States:** `active`, `superseded`, `cancelled`, `expired`.  
- **Supersession:** Indicated in metadata, not by altering the URN.  
-->
- **Persistence:** URNs generally remain valid indefinitely.

---

## 7. Resolution

TBD
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
TBD
```
---

## 10. Security and Privacy

- Identifiers themselves shall not contain personal data nor reveal any sensitive data of the resource identified.  
- Resolution services, if applied should use HTTPS.

---

## 11. Change Control

- This specification is maintained by the namespace owner 
- Historical URNs remain valid forever.

---

## 12. Explicit and implicit documentation of namespaces

**Each namespace, including sub-namespaces, shall have a defined owner, who is responsible for defining the purpose, scope and management of the namespace.**

All namespaces are formally defined using the tempate and including the formal **Augmented Backus–Naur Form (ABNF)**.

When a comonent within a definition permits the colon character (:) in its value, this MUST NOT be used in such a way, that a un-documented namespace is formed. Use of the colon (:) is allowed when a sub-namespace is explicitly defined and documented, or implicit within the top-level rule of the definition.

### Explicit ABNF definition
In cases where a namespace allows for subsequent namespaces to be created, by defining a component allowing the use of colon (:), each allowed sub-namespace must be explicitly defined according to the rules set up for documenting and defining URN and MRN- namespaces. Each subsequent namespace within such a hierarchy must be explicitly defined as a long as a component accepts the use of colon.

Example:
```
TBD
```
	
### Implicit ABNF definition
Implicit ABNF definition means, that additional sub-namespaces are defined as separate components within the top-level rule of the ABNF definition of a namespace. Implicit definition is used in cases, where a rule-based approach for namespacing is needed. When implicit definition is used, the components cannot allow the use of colon (:) wihtin the string.

Example: The imaginary namespace urn:mrn:fin:enc allows an identifier, that can also serve as a namespace for optional edition and update information. As colon are not allowed within the components themselves, subsequent namespaces cannot be created. The top-level definition should contain the needed guidance on using all the sub-namespaces the definition allows for. 

```
; Definition of ENC namespace with optional edition and update components
URN-MRN-FIN-ENC = "urn:mrn:fin:enc:" identifier [ ":" edition ":" update ]

; ENC chart identifier
identifier       = alphanum *(31*(alphanum / "-") alphanum)  

; Edition of the ENC chart
edition          = "ed" 2*DIGIT       

; Update of the ENC chart
update           = "upd" 2*DIGIT  

```

The implicit definition above allows for:
•	Identifying an ENC- chart by its identifier
o	urn:mrn:enc:BOBS34F

•	Identifying a specific edition and update of the chart by adding data. In this case, the chart identifier forms a namespace, that can hold identifiers for edition and update.
o	urn:mrn:enc:BOBS34F:2:0

## 13. References

- [RFC 8141: Uniform Resource Names (URNs)](https://www.rfc-editor.org/rfc/rfc8141)  
- [IANA URN Namespaces Registry](https://www.iana.org/assignments/urn-namespaces/)  
- [IALA MRN Guidelines](https://www.iala-aism.org/)  
