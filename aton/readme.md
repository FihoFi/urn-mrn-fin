# URN:MRN:FIN:ATON:
<!--ADD: Date updated-->
Updated: 2026-01-15

## 1. Purpose and Scope

<!--ADD: definitions of the namespace-->
This specification defines the subnamespace  
```
urn:mrn:fin:aton:
```
for use in identifying Finnish Aids to Navigation and other aspects related to these Aids.

- **Scope:** Persistent, globally unique identifiers for Aids to Navigation and related equipment.  
- **Out of scope:** Aids to Navigation which are not given an identifier by FTIA and components of equipment not covered within a sub-namespace.

---

## 2. Authority
<!--ADD: owner and point of contact-->
- **Namespace owner:** Finnish Transport Infrastructure Agency (FTIA)  
- **Contact:** tuomas.martikainen@vayla.fi 
- **Change control:** The namespace owner maintains this specificaton, including changes and rules for assigning identifiers.

---

## 3. Namespace Structure

**General form:**
```
"urn:mrn:fin:aton:" <aspect> ":" <identifier>
```
**Segments:**
- `<aspect>` - The aspect defines the particular aspect or characteristic of an Aids to Navigation. The aspect might be identification of the AtoN itself, or a structure, equipment or any other component or characteristic. Aspects can be added, and only aspects defined within this documentation should be used.
  
- `<identifier>` - The identifier that uniquely identifies the given aspect. Each aspect has its own set of identifiers, which are manily managed within an external process.

### Defined aspect and identifier combinations

| aspect      |identifier         | notes        |
|-------------|-------------------|-----------------------|
| id          | aton-number       | Identifies an Aids to Navigation by the national AtoN- number.     |
| light       | light-identifier  | Identifies a Light by the number in the national register. |


---

## 4. Syntax Definition

<!--ADD: ABNF definition of the namespace-->

**ABNF:**
```
mrn-fin-aton = "urn:mrn:fin:aton:" aspect ":" identifier

aspect       = "id" / "light"
       ; the aspect of an AtoN can include identification of the AtoN itself or any components, equipment or characteristic thereof. 
       ; list of aspects can be extended by adding to this documentation

identifier   = aton-number / light-identifier
       ; when aspect is id, identifier is an aton-number
       : when aspect is light, identifier is a light-identifier

aton-number      = alphanum
       ; aton-number is used with aspect: id
       ; the aton-number is the number given by FTIA to an AidsToNavigation within the national AtoN- database
       ; rules for assigning and uniqueness follows the external process set up by FTIA
       ; aton-number is a positive integer expressed without leading zeros

light-identifier = alphanum
       ; light-identifier is used with aspect: light
       ; the light-identifier is the number given by FTIA to a light within the national AtoN- database
       ; rules for assigning and uniqueness follows the external process set up by FTIA
       ; light-identifier is a positive integer expressed without leading zeros
```

## 5. Assignment & Uniqueness

<!--ADD: data to replace XXX-->

- **Assignement:** Identifiers are assigned by FTIA, mainly corresponding wioth the identifiers assigne in the national AtoN- database. 
- **Issuing authority:**  Finnish Transport and Infrastructure Agency (FTIA)
- **Uniqueness rule:**   Identifiers within each sub-namespace (aspect) must point to only one resource, although each reasource may have multiple identifiers. 
- **Persistence:** Rules for assigining and re-using identifiers of identifiers, follows the rules by the external process within the natinal AtoN- database. 

---

## 6. Lifecycle

- **Persistence:** URNs remain valid indefinitely, although an assigned URN might point to a resource that is no longer available.
---

## 7. Resolution
<!--ADD: resolution data-->
---

## 8. Syntax & Comparison Rules

- Identifiers are case-insensitive
- Numeric identifiers are generally expressed without (non‑significant) leading zeros
---

## 9. Examples

<!--ADD: examples-->
```
Identification of Aids to Navigation using the national number:
urn:mrn:fin:aton:id:12345

Identification of light equipment: 
urn:mrn:fin:aton:light:98765
```
---

## 10. Security and Privacy

---

## 11. Change Control

- This specification is maintained by the namespace owner with support by the OID-owner.
- Any resources a URN within this namespace points to, might become temporarily or peramantently unavailable, or change substantially.

---

## 12. References

- https://github.com/FihoFi/urn-mrn-fin/
<!--ADD: additiona references-->
