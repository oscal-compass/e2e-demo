# End-to-end Demo - CNCF OSCAL Compass
End-to-end Demo - CNCF OSCAL Compass

#### Overview

This end-to-end demo shows use of CNCF OSCAL Compass compliance-trestle and agile-authoring for (continuous) compliance standardization and automation.

<img src="images/e2e-demo.drawio.png" width="100%" />

##### Catalog

- Shown is CIS Catalog v8, which is already available in OSCAL format.
- This repo is used as the "source" for dependent repos needing this catalog.
- In some cases, the OSCAL format of the catalog is not available. In such circumstances, the Catalog repo can be used to do the transformation from the original source format into OSCAL using compliance-trestle tools.

##### Profile

- Shown is selected controls from CIS catalog.
- Use markdown editing to add guidance and assemble revised OSCAL profile.

##### Component Definition

- Comprises 2 parts: 
    - RHEL9 software (from CIS Benchmarks) and 
    - OSCO validation (from Compliance as Code)
- trestle transformer is used to transform RHEL9 CIS Benchmark to OSCAL Component Definition

##### Mapping

- Shown is *future* mapping model, for re-use of results from CISb to get posture for NIST 800-53.
