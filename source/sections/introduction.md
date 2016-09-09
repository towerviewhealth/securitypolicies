# Introduction

TowerView Health, Inc ("TowerView Health") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As providers of compliant, hosted infrastructure used by health technology vendors, developers, designers, agencies, custom development shops, and enterprises, TowerView Health strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by TowerView Health to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for TowerView Health Customers.

TowerView Health provides secure and compliant cloud-based software. This hosted software provides dashboards for medication management to patients, care coordinators, and pharmacies. 

## Software System

Patients and caregivers utilize the TowerView Health dashboard to view medication adherence information reported by their electronic pillbox. TowerView Health makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of patient through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, OSSEC throughout the Platform, etc).

## TowerView Health Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS). The network components and supporting network infrastructure are contained within AWS infrastructures and managed by Amazon. TowerView Health does not have physical access into the network components. The TowerView Health environment consists of Cisco firewalls, Node, twistd, and nginx web servers, MongoDB database servers, Logstash logging servers, and Linux Ubuntu monitoring servers.

Within the TowerView Health Platform on AWS, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers. TowerView Health assumes that patient data *may* collected during enrollment process is PHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

The result of segmentation strategies employed by TowerView Health effectively create RFC 1918, or dedicated, private segmented and separated networks and IP spaces, for each healthplan customer.

Additionally, IPtables is used on each each server for logical segmentation. IPtables is configured to restrict access to only justified ports and protocols. TowerView Health has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an SSL encrypted session.

The Nginx servers, machine server, Kibana servers are externally facing and accessible via the Internet. The database servers, where the ePHI resides, are located on the internal TowerView Health network and can only be accessed directly over an SSH connection through the production host. The access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business justified reason. Remote access to the internal servers is not accessible except through the load balancers and bastion host.

## Version Control

Policies were last updated September 9th, 2016.
