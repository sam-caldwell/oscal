OSCAL Experimenting
===================

## Objectives
1. Create a proof of concept golang program which will consume an OSCAL definition of
   NIST SP-800-53 Rev. 5 and produce the corresponding golang structs and methods.  These
   can then be used for more tools.
2. Create a proof of concept golang program that will consume an OSCAL definition of 
   NIST SP-800-53 Rev. 5 and connect to Atlassian JIRA to create a JIRA GRC project populated
   with ticket types, and ticket type hierarchies representing the controls for the standard.
3. Create a mapping tool for mapping two or more regulatory schemes to a unified specification
   which can be consumed by the first two tools.
4. Create a proof of concept golang program that will query Atlassian JIRA and create an OSCAL
   YAML representation of the current state of the compliance program defined in its GRC program.


Aspirational goals
1. Extend OSCAL to allow controls to be mapped to automations for collecting evidence of
   compliance.  This extended definition should allow the specification of tools and the 
   interface between the tools and the data collection mechanism (e.g. JIRA).