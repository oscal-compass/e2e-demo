# End-to-end Demo - CNCF OSCAL Compass

#### Overview

This end-to-end demo shows use of CNCF OSCAL Compass compliance-trestle and agile-authoring for (continuous) compliance standardization and automation.

<img src="images/e2e-demo.drawio.png" width="100%" />

##### Catalog

[repo](https://github.com/oscal-compass/e2e-demo-catalog)

- Shown is NIST 800-53, which is already available in [OSCAL format](https://github.com/usnistgov/oscal-content/tree/main/nist.gov/SP800-53/rev5/json).
- The present repo is used as the "source" for dependent repos needing this catalog.

Note: In some cases, the OSCAL format of a catalog is not available. In such circumstances, the Catalog repo itself can be used to do the transformation from the original source format into OSCAL using compliance-trestle and agile-authoring tools.

##### Profile

[repo](https://github.com/oscal-compass/e2e-demo-profile)

- Shown is selected controls from NIST 800-538 catalog.
- Use markdown editing to add guidance and assemble revised OSCAL profile.

##### Component Definition

[repo](https://github.com/oscal-compass/e2e-demo-cd)

- Comprises 2 parts: 
    - Ubuntu software component definition
    - OSCO validation component definition

##### System Security Plan

[repo](https://github.com/oscal-compass/e2e-demo-ssp)

- Shown is selected SSP comprising Ubuntu component definition.
- Use markdown editing to add guidance and assemble revised OSCAL SSP.

##### Mapping

[repo](https://github.com/oscal-compass/e2e-demo-mapping)

- Shown is *future* mapping model, for re-use of results from NIST 800-53 to get posture for other compliance program(s), such as HIPAA, GDPR, FedRAMP, SOC2...


##### XCCDF Results for UBUNTU

[repo](https://github.com/oscal-compass/e2e-demo-xccdf-ubuntu)

- Repo comprises XCCDF results for Ubuntu system.


##### Compliance posture

[repo](https://github.com/oscal-compass/e2e-demo-compliance-posture)

- Repo comprises compliance posture for Ubuntu system.

-----
-----

##### C2P

Integration with C2P.

Reference: [compliance-to-policy-go](https://github.com/oscal-compass/compliance-to-policy-go)

<img src="images/e2e-demo.c2p.drawio.png" width="100%" />


The above setup imagines that the Compliance Posture Repo has access to the subject.

-----
-----

##### C2P (using VM subject)

Integration with C2P.

Reference: [compliance-to-policy-go](https://github.com/oscal-compass/compliance-to-policy-go)

<img src="images/e2e-demo.c2p-vm.drawio.png" width="100%" />



The above setup imagines that the Compliance Posture is cloned onto a Manager, and the Manager has access to the subject (e.g., a local VM).


##### Steps to create Secure Server VM (subject of compliance posture inquiry)

- Download and install VirtualBox from - https://www.virtualbox.org/wiki/Downloads This is the Oracle hypervisor that will run the VM.
- Download and install Vagrant from - https://developer.hashicorp.com/vagrant/install Vagrant is a developers tool for automating the creation of lightweight, reproducible and portable virtual environments via command-line
- Download [Vagrantfile](resources/Vagrantfile)
- Execute “vagrant up”. This will download (first time only) and start the VM.

##### Continued, steps to check oscap on Secure Server VM

- Execute “vagrant ssh”.
- `vagrant@vagrant:~$ sudo oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_cis_level2_workstation --results /tmp/results.xml --report /tmp/report.html /usr/share/xml/scap/ssg/content/ssg-ubuntu2404-ds.xml`

##### Continued, steps to exit and shutdown VM

- `vagrant@vagrant:~$ exit`
- Execute “vagrant halt”.

