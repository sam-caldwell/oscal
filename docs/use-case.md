Use Case
========

`tools/cmd/oscal2go`:
* Creates OSCAL structures and methods from an OSCAL YAML input.
* The output is created in `tools/lib/oscal`

`tools/cmd/oscal2jira`:
* Using OSCAL golang files to create a JIRA GRC project and its related control tickets.

`tools/cmd/jira2oscal`:
* Collects JIRA OSCAL GRC project ticket information and writes an OSCAL YAML status report.

`tools/cmd/oscalMapper`:
* Using two or more OSCAL YAML sources and a YAML Mapping file created by `mapControls`, the
  `oscalMapper` command will parse the source OSCAL YAML files and write a combined OSCAL
  YAML standard specification with mappings between related controls.

`tools/cmd/mapControls`:
* Create a YAML Mapping file that defines how controls from two OSCAL YAML files relate to one
  another.  For example, NIST SP-800-53 AC-1 is equivalent to PCI 1.1.1, and thus this command
  will produce a YAML file that defines the standards and the equivalent mapping.
* The mapping tool should also allow a rationale to be provided in the mapping.
* The mapping tool should allow for cases where two similar controls are related but not equal
  and which will be the 'preferred' control to be observed over the other.

```yaml
standards:
  - nist: "NIST SP-800-53 rev. 5"
  - pci: "PCI-DSS 4.0"
mappings:
  - nist: "AC-1"
    pci: "1.1.1"
    relationship: "equivalent"
    rationale: "Both controls address access control for systems"
  - nist: "IA-2"
    pci: "3.2.1"
    relationship: "related"
    preference: "nist"
    rationale: "IA-2 relates to identification and authentication, which is covered by 3.2.1 in PCI-DSS"
```