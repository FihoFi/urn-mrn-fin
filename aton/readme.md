# URN:MRN:FIN:ATON:
<!--ADD: Date updated-->
Updated: 2025-11-03

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
- **Namespace owner:** Finnish Transport Infrastructure Agenct (FTIA)  
- **Contact:** tuomas.martikainen@vayla.fi 
- **Change control:** The namespace owner maintains this specificaton, including changes and rules for assigning identifiers.

---

## 3. Namespace Structure


**General form:**
<!--ADD: general form description
```
"urn:mrn:fin:aton:" <aspect> ":" <identifier>
```

**Segments:**
<!--ADD: definition of the segments (components)-->

- `<aspect>` - The aspect defines the particular aspect or characteristic of an Aids to NAvigation. The aspect might be identifiaction of the "idea" of the AtoN itself, the structure, equipment or any other component. Only aspects defined within this documentationcan be used.
  
- `<identifier>` - The identifier that uniquely identifies the given aspect. Each aspect has its own set of identifiers, which are manily managet within an external process. 

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
       ; the aton-number is the numbr given by FTIA to any AidsToNavigation within the national AtoN- database
       ; rules for assigning and uniqueness follows those the external process of assigning numbers

light-identifier = alphanum
       ; light-identifier is used with aspect: light
       ; the light-identifier is the kinternal number given to a light within the national AtoN- database
       ; rules for assigning and uniqueness follows those the external process of assigning numbers
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
---

## 9. Examples

<!--ADD: examples-->
```
Identification of Aids to Navigation using the national number:
urn:mrn:fin:aton:id:12345

Identification of light equipment: 
urn:mrn:fin:aton:light:98765
---

## 10. Security and Privacy

---

## 11. Change Control

- This specification is maintained by the namespace owner 
- Historical URNs remain valid forever.

---

## 12. References

- https://github.com/FihoFi/urn-mrn-fin/
<!--ADD: additiona references-->
