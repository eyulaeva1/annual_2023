# annual_2023
---
title: "CAIDA's Annual Report for 2023"
nickname: "2023 Annual"
date: 2023-12-31
summary: "A report on CAIDA research initiatives, project progress and results, data sets, tool development, publications, presentations, workshops, web site statistics, and operating expenses for 2023." 
pageMenu: 
includeJS: ["tinysort.min"]
headinfo: |
  <link rel="stylesheet" href="/css/annualreports.css" />
  <script src="/js/annualreports.js"></script>
  <script type="text/javascript">
    $(document).ready(function()
    {
        tinysort("#fundingsort>li", ":not([class=dontsort])");
    }  
    );
  </script>

pageSynopsis: |
  A report on CAIDA research initiatives, project progress and results, data sets, tool development, publications, presentations, workshops, web site statistics, and operating expenses for 2023. 
---

Mission Statement: CAIDA investigates practical and theoretical aspects of the Internet, focusing on activities that:   
  
* provide insights into the macroscopic function of Internet infrastructure, behavior, usage, and evolution,
* foster a collaborative environment in which data can be acquired, analyzed, and (as appropriate) shared,
* improve the integrity of the field of Internet science, 
* inform science, technology, and communications public policies.

---
{{< load-photoswipe >}}
## Executive Summary

This annual report summarizes CAIDA's activities for 2023 in the areas
of research, infrastructure, data collection and analysis.   

[RESEARCH section]: # (==================================================================================================)
## Research and Analysis

<!-- 
[---Security, Stability, and Resilience of the Internet's underlying transports systems]: # (---------------------------------------------)
### Security, Stability, and Resilience (SSR) of the Internet's underlying transport systems 
--> 
[---Network Measurement and Analysis]: # (---------------------------------------------)
### Network Measurement and Analysis

#### Expanding BGP Data Horizons
Rapid Internet growth challenges data collection for interdomain routing analysis. To address this challeng we worked with UCLouvain (Belgium) researchers on the reconceptualization of the public BGP data collection architectures, introducing an overshoot-and-discard strategy. This approach accommodates a significant increase in vantage points, by discarding redundant data shortly after its collection. We evaluated the method's effectiveness in detecting two important phenomena using BGP data: AS-topology mapping and hijacks. Our approach, applicable to various Internet data types, introduces a promising avenue for future Internet measurement research. ([Internet Science Moonshot: Expanding BGP Data Horizons](https://catalog.caida.org/details/paper/2023_internet_science_moonshot/), ACM)

#### Investigating Irregularities in the Internet Routing Registry
{{< figure src="/about/annualreports/2023/images/2023_irregularities_in_internet_routing_registry.png" width="300px" class="float-right" caption="Illustration of the threat model where attackers register false IRR records." attr="(IRRegularities in the Internet Routing Registry, IMC)" attrlink="https://catalog.caida.org/details/paper/2023_irregularities_in_internet_routing_registry/" >}}
The Internet Routing Registry (IRR), established in the 1990s for routing policy registration and BGP message validation, remains widely used for routing security despite newer alternatives. However, lacking a strict validation standard and facing coordination issues among providers, the IRR is susceptible to inaccuracies. This paper conducts a 1.5-year longitudinal analysis, revealing 34,199 irregular IRR records, with 6,373 potentially suspicious instances, highlighting the ongoing challenge of false registrations and potential security risks in the Internet routing system. ([IRRegularities in the Internet Routing Registry](https://catalog.caida.org/details/paper/2023_irregularities_in_internet_routing_registry/), IMC)

#### Classifying BGP Communities
{{< figure src="/about/annualreports/2023/images/2023_coarse_grained_inference_bgp.png" width="300px" class="float-right" caption="@@@" attr="(Coarse-grained Inference of BGP Community Intent, IMC)" attrlink="https://catalog.caida.org/details/paper/2023_coarse_grained_inference_bgp/" >}}
We explored BGP Communities, which serve as a vital signaling mechanism within BGP routers. These communities play a crucial role in enhancing scalability and automating processes within expansive networks. By grasping the concept of communities, one gains insight into the intricacies of Internet routing dynamics. However, the meanings behind these communities are often undisclosed, necessitating inference.
As a first step toward automating the inference of BGP community meanings, we formulated an algorithm capable of distinguishing the two coarse-grained community categories discerning two primary community categories: 'information' and 'action'. Our algorithm demonstrated a remarkable accuracy rate of 96%, thereby enhancing the precision of existing methodologies in this domain. We presented our work at the Internet Measurement Conference (IMC) in October, where our research received recognition as runners-up for the best paper award. As part of our commitment to fostering community-driven progress, we have made our code and data openly accessible.([Coarse-grained Inference of BGP Community Intent](https://catalog.caida.org/details/paper/2023_coarse_grained_inference_bgp/), IMC)

#### Utilizing RPKI for Validation of BGP Messages
The Border Gateway Protocol (BGP) includes no mechanism to verify the correctness of routing information exchanged between networks. To defend against unauthorized use of address space, the IETF developed the Resource Public Key Infrastructure (RPKI), a cryptographically attested database system that facilitates validation of BGP messages. Networks can use RPKI to check whether the Autonomous System (AS) at the origin of the AS path in a BGP announcement is authorized to originate the IP prefixes being announced. ([Taking the Low Road: How RPKI Invalids Propagate](https://catalog.caida.org/details/paper/2023_taking_low_road/), SIGCOMM Poster)

#### QUINCE
We are designing and implementing a crowdsourcing-based platform (QUINCE) to measure the QoE of video streaming and video conferencing applications.  We dedicated efforts to seamlessly integrate the QUINCE experiment platform withpublic cloud platforms to automate the deployment of experiments reactively ingeographically diverse cloud regions. Leveraging CloudBank, we explored variousservices offered by Amazon AWS, Microsoft Azure, and Google Cloud Platform.Specifically, we evaluated different software and APIs in terms of ease of use,deployment speed, and functionality for deploying virtual machines (VMs) andDocker images on AWS and Azure to support live video streaming and videoconferencing experiments. These tools enabled us to develop a customized webconsole in QUINCE to monitor the use of cloud resources in real-time. We prototyped crowdsourcing-based video conferencing experiments and are addressing challenges in operationalizing the prototype. We enhanced the QUINCE prototype by introducing more gamification features to boost the intrinsic motivation of subjects. Apart from improving visualization components, we introduced new gamification features. 


[---Internet Routing and Security]: # (---------------------------------------------)
### Internet Routing and Security

#### Assessing Connectivity Vulnerabilities
{{< figure src="/about/annualreports/2023/images/2023_on_importance_being_as.png" width="300px" class="float-right" caption="Contrasting the calculations for Customer Cone (CC) and AS Hegemony (AH) for an AS topology with provider-to-customer and peer-to-peer relationships." attr="(On the Importance of Being an AS, IMC)" attrlink="https://catalog.caida.org/details/paper/2023_on_importance_being_as/" >}}

Geopolitical events underscore the importance of Internet infrastructure control for economic and defense purposes. To assess countries vulnerable to Internet connectivity issues due to reliance on foreign networks, the study adapts global BGP-based metrics for regional analysis. Overcoming challenges like geolocation and incomplete data, the approach involves downsampling public routing data to individual countries. Case studies on Australia, Japan, Russia, Taiwan, and the United States reveal insights into telecommunications market concentration and interdependence. The researchers plan to share their code, inferences, and datasets for reproducibility. ([On the Importance of Being an AS: An Approach to Country-Level AS Rankings](https://catalog.caida.org/details/paper/2023_on_importance_being_as/), IMC)

#### Improving Routing Security Via Trust Zones
We introduce two related concepts that we believe can lead to improved security of the global Internet routing system (the Border Gateway Protocol or BGP). BGP suffers from a well-documented vulnerability: a network (termed an Autonomous System or AS) can falsely announce that it hosts or is on the path to a block of addresses that it does not in fact have the authority to announce. Routers that accept a false route announcement – known as a route hijack – will deflect traffic intended for addresses in that block to a rogue AS. ([A path forward: Improving Internet routing security by enabling trust zones](https://catalog.caida.org/details/paper/2023_a_path_forward/), FCC)

#### Assessing Physical Risks to Internet Access Networks
Regional access networks, crucial for connecting users to the Internet, face vulnerabilities due to economic and architectural constraints, leaving them susceptible to targeted physical attacks. The study combines novel techniques for analyzing access-network infrastructure with large-scale outage measurements to demonstrate the feasibility and quantify potential impacts of such attacks. The research provides insights into the physical attack surfaces and resiliency limits of regional access networks, suggesting potential mitigation approaches while acknowledging drawbacks identified by network operators. The empirical evaluation aims to inform risk assessments, operational practices, and stimulate further analyses of this critical infrastructure. ([Access Denied: Assessing Physical Risks to Internet Access Networks](https://catalog.caida.org/details/paper/2023_access_denied/), USENIX Security Symposium)
<!--- Potentially useful visuals in this paper --->

#### AVOID
<!-- add avoid image -->
In collaboration with Alexander Marder now at Johns Hopkins University, CAIDA is prototyping an automated system that helps Department of Defense (DOD) operators who want to communicate with 5G devices by avoiding nation-state adversaries and moving communications to safe paths. The design is user-based, so it will be the result of interviews with end-users and stakeholders.  This is called the AVOID system: Automated Verification Of Internet Data-paths. In 2023, we  spent considerable effort obtaining preliminary results to demonstrate the power of
our design. We focused primarily on designing, training, and testing a base station vendor
classifier, as well as demonstrating the power of our geolocation-based approach. We filed a provisional patent to protect new intellectual property developed under this project.

#### Cloud-Native Internet Measurement Pipeline
With Alexander Marder at Johns Hopkins University, we developed a software pipeline to deploy measurements on public cloud platforms at scale. The pipeline integrates modern software stacks, enabling us to provision multiple measurement virtual machines (VMs) across cloud platforms and securely collect measurement results. Leveraging this pipeline, we conducted large-scale traceroute measurements to geolocate 2.5 million IP addresses discovered by CAIDA’s Macroscopic InternetTopology Data Kit (ITDK) from VMs we set up in 85 data centers from three major cloud providers (Amazon AWS, Google GCP, and Microsoft Azure). We inferred the geolocation of the IPs using [hoiho](https://catalog.caida.org/dataset/hoiho), which analyzes geolocation hints in hostnames and cross-validates with network latency. Conducting measurements from diverse vantage points could improve the accuracy of the geolocation inference. 

<!-- save for 2024
#### Empirical Characterization of Ookla's Speed Test Platform
Using speed test server information that CAIDA has been collecting for three years, we characterized the Ookla speed test infrastructure. By combining APNIC’s AS population dataset, wefound that coverage of on-net test servers (i.e., test servers in the same AS as end-users) in the U.S. covered less than 70% of the Internet population. In contrast, on-net server deployment in counties served by a few national ISPs (e.g., India, Mexico,and the Philippines) achieved almost 100% population coverage. We found that several countries (e.g., China, Japan, Ukraine, and Russia) lost a significant number of test servers over the last three years. Our preliminary investigation showed thatthe geopolitical conflict between the U.S. and Russia played a role in the serverdeployment. Some Russian telecommunication companies removed a significant number of test servers since 2022 when the U.S. imposed sanctions on them. We also found an update of Ookla’s server hosting policy potentially caused the removal of test servers in China and Japan. ([Empirical Characterization of Ookla's Speed Test Platform: Analyzing Server Deployment, Policy Impact, and User Coverage](https://catalog.caida.org/paper/2024_empirical_characterization_ooklas_speed_test), CCWC)
-->

[---Legal and Regulatory Impact]: # (---------------------------------------------)
### Legal and Regulatory Impact

#### Elaborating on Security Issues Discussed by the FCC
On January 20, 2022, a meeting took place between David Clark (CSAIL/MIT), KC Claffy, Mr. Ken Carlberg, and Padma Krishnaswamy from the FCC to discuss the Notice of Inquiry on Secure Internet Routing. The meeting addressed various comments reflecting the widespread understanding of the severity of routing security issues. While U.S. government agencies advocate FCC action, some emphasize the challenges of regulation, the government's adoption of security practices, and the importance of non-regulatory approaches. The discussion highlighted the increasing tension on the topic amid prolonged multistakeholder efforts and the growing risk of BGP hijacks affecting even major corporations. The researchers provided additional perspectives based on their academic expertise in Internet architecture and routing. ([Notice of Ex Parte Meeting, Secure Internet Routing](https://catalog.caida.org/details/paper/2023_notice_of_ex_parte_meeting_fcc_22_90/), FCC)

#### Reporting on the EU Digital Services Act
The EU Digital Services Act (DSA) is intended to reduce the risks and challenges for individual recipients of Digital Information services, in particular what are described as intermediate services. The regulation imposes specific obligations on platforms that allow online trading, and expanded obligations on very large online platforms and very large search engines. A second goal of the DSA is to provide a single, harmonized regulatory framework for the Union, and to preempt the creation of divergent regulatory structures by individual States. The regulation states that Member States should not adopt or maintain additional national requirements relating to the matters falling within the scope of this Regulation.([The EU Digital Services Act and Academic Research - Technical Report](https://catalog.caida.org/details/paper/2023_eu_digital_services_act/), CAIDA)

[---Data and Ontology Mapping]: # (---------------------------------------------)
### Data and Ontology Mapping

#### Mapping Ontologies onto Dataset Schemas
The goal of this proposal, Annotated Schema (AS), is to provide a limited ontology of annotations for dataset metadata that inform a prospective user of the classes, properties, and identifiers contained in the data. The intended audience of this document includes Data Curators (annotators) who want to create meaningful dataset descriptions, and those searching for data sets in our catalog. ([Annotated Schema: Mapping Ontologies onto Dataset Schemas](https://catalog.caida.org/details/paper/2023_annotated_schema/), CAIDA)


[MEASINFRA section]: # (==================================================================================================)
## Measurement Infrastructure and Data Sharing Projects

### Designing a Global Measurement Infrastructure to Improve Internet Security (GMI3S)
{{< figure src="/funding/msri-gmi3s/gmi3s-structure-overview.png" width="300px" class="float-right" caption="Overview of the GMI3S structure" >}}

 
We have been continuing our efforts to enhance our Internet measurements, data analytics, and data sharing platforms and pipelines. These improvements aim to streamline the collection and curation of infrastructure data, making it easier to query, integrate, share, and analyze. Our ongoing work is guided by the framework of the GMI Design Project (Designing a Global Measurement Infrastructure to Improve Internet Security, or GMI3S).  The objective of the GMI project is to design and prototype a new generation of measurement infrastructure for the Internet. 
Specifically, our attention is on security vulnerabilities (and consequential harms) that arise in the packet carriage layer of the Internet.
We focus on the following system components:
 (1) The addressing architecture of the Internet, and systems to support address allocation,
management, and use; (2) The global routing protocol of the Internet, the Border Gateway Protocol, or BGP; (3) The Domain Name System, or DNS, which maps from high-level names to IP addresses; (4) The Certificate Authority system, which manages encryption keys for applications.
([GMI3S Design Project website](https://gmi3s.caida.org/))
Below we list the project 2023 progress highlights. 

#### Active Measurements
@@from M24 and M30 reports 
##### Archipelago 
@@rewrite 
We continued to maintain the [Archipelago (Ark)](/projects/ark/) active measurement platform as needed to inform our next generation active measurement infrastructure design effort.  Ark monitors continue to provide raw data for most of our macroscopic Internet data sets.  In an effort to reevaluate our Ark infrastructure going forward, we began evaluating other single-board computers apart from the Raspberry Pi to discover if any viable alternatives that have emerged since the initial deployment of Ark almost two decades ago.
##### DSL
##### Virtualization
##### Deployment on IXP
#####  AIMS workshops @@does this section belong to some other part ????

##### FANTAIL
##### PERISCOPE
##### SCAMPER
##### Geoping

#### BGP Measurements
@@from M24 and M30 reports
Include GILL 

##### AS Rank 
AS Rank integrates heterogeneous datasets, including [AS-relationships](https://catalog.caida.org/dataset/as_relationships_serial_1), inferred relationships, customer cones, [AS to organization mapping](https://catalog.caida.org/dataset/as_organizations), [Netacuity geolocation](https://www.digitalelement.com/solutions/location-targeting/netacuity/?utm_campaign=GF_Brand_Search&utm_source=google_c&utm_medium=ppc&utm_content=656665743792&utm_term=e_netacuity&adgroupid=155354887184&gad=1&gclid=CjwKCAjwzJmlBhBBEiwAEJyLu-DqF3-OrdJq_s7Ll5tlQKe8h1uRM3AAiUBxfAgbi6b6PA7y5hv4ixoC3BwQAvD_BwE), and more, to generate a unified and comprehensive perspective of the Internet's Autonomous Systems (ASes). This unified view allows for a better understanding of the relationships, hierarchy, and characteristics of ASes within the global Internet infrastructure. Seeking operator ground truth in our rankings, we worked on an interface to solicit feedback and corrections from the community. We continue to update AS Rank’s inferences with operator ground truth, increasing the accuracy of the presented data.  

##### AS to Organization mapping
We continued updating the as2org data set every quarter. <span class="old">In addition, we manually integrated seven annotations provided by operators and other Internet experts.</span>
##### Prefix2AS

##### BGP2GO 
BGP metadata and BGP2GO to facilitate access and sharing of relevant MRT files.  
In the context of CAIDA Science Gateway, we generate monthly metadata databases (BGPMeta) out of BGP data that contain information about where to find prefixes, ASNs, and communities. BGP2GO is an application for the metadata. It allows a potential consumer of BGP data to select, download and process only the relevant data.

In 2023, there have been various extensions to / activities around BGP2GO. BGP2GO and BGPMeta run stable and uninterrupted since more than a year, while new data is being ingested every 15 minutes. It is being used by people from industry (e.g., Fastly) as well as researchers in the community. We built website peer stats to inform about the update volume coming from routeviews collector peers. It makes use of the metadata database (BGPmeta).  We created a production version that sits behind keycloak (https://bgp2go.caida.org/) such that only authorized users can access BGP2GO. We worked on improving the existing web interface by porting it to React. We generated a database for allocation statistics taken from the five RIRs (Regional Internet Registries), i.e., ARIN, RIPE, APNIC, AFRINIC, and LACNIC. This database informs about when a prefix or ASN have been allocated or assigned to another Internet Registry or directly to the customer. This database is being updated on a daily basis and will be integrated into BGP2GO soon. We also performed preliminary analysis of public open-intel DNS data to show the feasability of integrating prefix activity in DNS with BGPMeta/BGP2GO.

##### BGP Communities

##### BGPStream
We continued limited support for the BGPStream broker, which is seeing growing use.  
@@kc -- not sure we need to include it 

#### DNS Measurements 

##### DNS Zone Database (DZDB) platform for querying DNS TLD zone files
CAIDA's DNS Zone Database (DZDB) is a platform providing access to time-series data derived from current and historical zone files provided by generic Top-Level Domains (gTLDs) participating in the Central Zone Data Service (CZDS) or directly by TLD Registry Operators in compliance with license agreements. We continued working with collaborator Ian Foster to transition the DZDB platform to CAIDA infrastructure and updated the import code to run on our systems. Researchers can query this database for domains, nameservers, IP addresses and more via the [DZDB API](https://dzdb.caida.org/api), whose documentation we significantly expanded.
@@add from M24&M30 reports

##### ICANN SSAC work party 
##### KINDNS
##### FCC --  zones of trust
 
#### Facilitating Advances in Network Topology Analysis (FANTAIL)
@@move to active measurements
We developed the Facilitating Advances in Network Topology Analysis (FANTAIL) system to facilitate discovery of the full potential value of massive raw Internet end-to-end path measurement data sets, allowing researchers to use high-level queries to perform data processing and analysis tasks on matching traces without owning/operating a cluster, and without learning big data programming. [FANTAIL](/projects/fantail/) is a four-component system: (1) an interactive web interface; (2) an API built on web standards; (3) a full-text search system based on Elasticsearch; and (4) a big data processing system based on Spark.  
In 2023, with FANTAIL robustly implemented and operationalized with improved data processing and query capabilities, we addressed technical challenges to enhance system stability  and performance. We facilitated sophisticated data analysis and visualization, aiding researchers in utilizing extensive data sets.  We optimized data storage and management, ensuring system reliability. We began limited access for FANTAIL to a small group of beta-testers in the research community, and await community feedback to inform our path forward.

##### Hoiho
@@move to BGP
Holistic Orthography of Internet Hostname Observations (Hoiho) is an open-source tool  released as a part of scamper. It uses CAIDA's Macroscopic Internet Topology Data Kit (ITDK) and observed round trip times to infer regular expressions that extract apparent geolocation hints from hostnames. The ITDK contains a large dataset of routers with annotated hostnames, which are used as input to Hoiho for its inference rules (encoded as regular expressions) that extract these annotations. In 2023, in response to user feedback, we expanded the documentation of the [web API for Hoiho](https://api.hoiho.caida.org/) that provides hostname-location lookups. 

Researchers at CAIDA worked on the geoping pipeline project, developing an algorithm and framework to effectively prune more than 90 percent of around 153 million tuples of RTT data without affecting the correctness of the hoiho algorithm to geolocate each router on the Internet, significantly improving performance and inferences.

##### Libipmeta to support querying for IP address metadata
@@kc -- did we do anything 
[Libipmeta](https://github.com/CAIDA/libipmeta) is a library to support the querying for historical and realtime IP metadata including CAIDA's geolocation information, Prefix-To-AS databases, and future metadata on IP addresses. This library has a companion [pyipmeta library](https://github.com/CAIDA/pyipmeta). We implemented a Golang-native version of ipmeta, to enable concurrent processing of data,  and used it to analyze network telescope traffic. Bugfixes reducing missing geolocation information and updating pyipmeta to the latest version of Python was released as version v3.2.1 this year.

##### Internet Topology Data Kit (ITDK)
Our ongoing collection of [Macroscopic Internet Topology Data Kits (ITDK)](/catalog/datasets/internet-topology-data-kit/) started in 2010 and now includes 23 Kits. In 2023 we published the 2023-03 ITDK.  These data sets contain router-level topologies generated from the [Ark IPv4 Routed /24 Topology Dataset](https://catalog.caida.org/dataset/ark_ipv4_traceroute).

#### IP Prefix to AS Mapping
One of CAIDA's most frequently requested datasets is its [RouteViews Prefix to AS Mapping Dataset for IPv4 and IPv6](https://www.caida.org/catalog/datasets/routeviews-prefix2as/) dataset. This dataset contains IPv4/IPv6 Prefix-to-Autonomous System (AS) mappings derived from the NSRC RouteViews Project, which gathers BGP updates from hundreds of vantage points around the world. CAIDA uses RouteViews BGP tables dumps (from one collector) to perform a longest-prefix match on observed prefixes, to produce daily snapshots of the Prefix to AS mapping. This daily updated dataset goes back to May 2005. <span class="old">We also did major refactoring, redesign, optimizations, output formatting, and code cleanup in the prefix2as code within BGPView (a BGPstream-based library). </span>
@@move to BGP Measurements
@@elena waiting for Ben's comments on "we stopped producing it bcs there were problems with RV rib files, But now we fixed the problem and restarted/backfilled the data and update it daily" 

##### MIDAR
We continued to maintain all backend and database components that use the MIDAR IPv4 alias resolution service. The [MIDAR web API](/projects/ark/vela/midar-api/) delivers access to MIDAR's functionality.  This tool is a pillar of our [Macroscopic Internet Topology Data Kits (ITDK)](/catalog/datasets/internet-topology-data-kit/).
@@move to active measurements 

##### PacketLab 
@@kc -- does it belong to active measurements? 

CAIDA continued to collaborate with UIUC's team (led by PI Kirill Levchenko) investigating a new technical approach to sharing network measurement infrastructure by developing an experimental interface to disparate measurement endpoints maintained by different research teams.  PacketLab is built on two key ideas: It moves the measurement logic out of the endpoint to a separate experiment control server, making each endpoint a lightweight packet source/sink. At the same time, it provides a way to delegate access to measurement endpoints while retaining fine-grained control over how one's endpoints are used by others, allowing research groups to share measurement infrastructure with each other with little overhead.  While the core design has limitations, a survey of recent Internet measurement studies and empirical comparisons with native implementations reveal that PacketLab produces similar results to native versions for various measurement types. The findings suggest that PacketLab could contribute to reproducing or extending approximately 16.4% of surveyed studies, covering measurements such as latency, throughput, network path, and non-timing data. ([Empirically Testing the PacketLab Model](https://catalog.caida.org/details/paper/2023_empirically_testing_packetlab_model/), IMC). UIUC released an updated Alpha version of the PacketLab software package at [pktlab.github.io](https://pktlab.github.io) for community evaluation. 

##### Periscope
@@move to active measurements
In 2023, the [Periscope Looking Glass API](https://www.caida.org/catalog/software/looking-glass-api/) continued public beta testing. We continued adapting the backend and API to support its use for access to scamper processes running on BGP collectors, and its integration with CAIDA's new Keycloak-based authentication/authorization framework.  

##### Spoofer 
@@move to active measurements
Spoofer is a suite of open-source software tools to assess and report on the deployment of source address validation (SAV) best anti-spoofing practices. This client-server system periodically tests a network's ability to both send and receive packets with forged source IP addresses (spoofed packets).  The CAIDA Spoofer Data API (https://api.spoofer.caida.org/) provides a public data interface to the publicly sharable data collected by the Spoofer service. We improved the API by allowing easier browser access to larger downloads of data for time series analysis. We also streamlined the process of notifying interested administrators when we detect spoofing in their network.

#### One-way traffic 

##### UCSD Network Telescope
summary of ARDC report https://ucsdcloud-my.sharepoint.com/:w:/g/personal/eyulaeva_ucsd_edu/EdsYQURC-exFvfkzGjKTXh4Bj2yLdeYrkGmJJ2w-bVhebA?e=NdJUhe
##### STARNOVA
##### DDoS paper


#### Two-way traffic

In October 2023 we  successful deployed  the two-way monitor at 100 GB link.  We are employing 16 streams that we then combine into one trace.The previous CryptoPAn  implementation did  not implement encryption of bitstrings of lengths other than 32; for example, it did not support the anonymization of 128-bit IPv6 addresses. We are now anonymizing IP with an updated version of the Crypto-PAn which
now anonymized all 128 bits.

@@elena revise – this is a description of the old process 
The trace is captured on the remote machine once a month, usually on the third Thursday of the month between 6:00pm and 7:00pm UTC (i.e. 11:00 am  in San Diego). The trace is captured in erf format. Packet stripping is done on the remote machine and takes half a day. The stripped data are stored in dag format. These are downloaded to our data server for further processing. The main step is anonymizing the data. Anonymized data are stored as pcap files. These are the files that are put online in the Anonymized Passive Internet traces dataasets. Additional processing includes deriving some statistics that are put online.
The data is then transferred and stored in SWIFT -- our cloud storage and is shared with vetted researchers. 
This restricted dataset is accompanied by publicly available metadata that contains the following fields: 
Monitor
Year and month (including a link to a graphical display of breakup by protocol, application, and country), Start time of trace (UTC),  Stop time of trace (UTC), Number of IPv4 packets, Number of IPv6 packets,
Unknown packets (as a fraction of total number of packets), Transmission rate in packets per second,
Transmission rate in bits per second,, Link load (as fraction of nominal maximum load for a 100 GB link (9.953×109 @@elena to clarify bits/s), Average packet size (bytes) (including a link to a graph of the packet size distribution)


[DATA section]: # (==================================================================================================)
## Data Collection Statistics: Topology and Traffic 

The slide deck, [CAIDA Measurement Data Infrastructure Overview](https://www.caida.org/catalog/media/2022_caida_measurement_data_infrastructure_overview/caida_measurement_data_infrastructure_overview.pdf) continues to summarize CAIDA datasets used for networking and security research.

The graphs presented here show the cumulative volume of data accrued over the last several years by our primary data collection infrastructures, [Archipelago](https://www.caida.org/projects/ark/) (Ark) and the [UCSD Network Telescope](https://www.caida.org/projects/network_telescope/).

{{< figure src="/about/annualreports/2023/images/ark_compressed_size_2007_2023.png" width="300px" class="float-right" caption="Compressed size of Ark topology measurements. Light green shading indicates the size of IPv4 team probing measurements, dark green -- the size of IPv4 prefix probing, blue -- IPv4 TSLP congestion, red -- IPv4 Border Mapping, purple -- IPv6 topology." >}}

{{< figure src="/about/annualreports/2023/images/ucsd_telescope_data_nersc_2003_2023.png" width="300px" class="float-right" caption="Compressed size of the UCSD Network Telescope raw data stored at NERSC." >}}

In 2023 CAIDA executed the following Ark measurements on an ongoing basis:

* IPv4 team probing: daily traceroutes to all routed /24 IPv4 networks – [Ark IPv4 Routed /24 Topology Dataset](https://catalog.caida.org/dataset/ark_ipv4_traceroute)
* IPv4 prefix probing: daily traceroutes to every BGP-announced IPv4 prefix from a subset of Ark monitors – [IPv4 Prefix-Probing Traceroute Dataset](https://catalog.caida.org/dataset/ark_ipv4_prefix_probing)
* IPv6 topology measurements collected by a subset of ark monitors that probe all announced IPv6 prefixes (/48 or shorter) once every 48 hours – [Ark IPv6 Topology Dataset](https://catalog.caida.org/dataset/ark_ipv6_traceroute)

<!-- * Congestion measurements (discontinued in 2023) aimed at detecting congestion on interdomain links of the networks hosting the Ark monitors. Congestion measurements are comprised of Time-Sequence Ping (TSP) measurements and Border Mapping (bdrmap) measurements<br/> --> 
In 2023 CAIDA captured about 1.3 PB of compressed Internet darknet traffic data.  As of January 2024, we collect about 1.7 TB of compressed data per day, more than 95% of which is Telescope (darknet) data. We archive raw telescope data at NERSC.
{{< clear-float both >}}

### CAIDA Resource Catalog

{{< figure src="/about/annualreports/2022/images/catalog_schematic.png" width="300px" class="float-right" caption="Schematic representation of the Resource Catalog architecture." >}}

In pursuit of the FAIR (findable, accessible, interoperable, reusable) principles of our scientific data infrastructure mission, we invested significant effort to make our data sets and associated resources more accessible to other researchers. We continued development of the [CAIDA Resource Catalog](https://catalog.caida.org), which provides a unified interface to metadata and relationships between datasets, papers, presentations, media, software,  and recipes (code and  instructions on how to solve various Internet security-related problems using datasets, tools and other objects indexed in catalog).  We added new types of resources (collections and presentations) and new metadata fields to facilitate discovery of resources. We created [collections](https://catalog.caida.org/search?query=types=collection), which are groups of resources by CAIDA topic or project.  We responded to community feedback by adding "suggestions" when searching and including a link to search instructions for [how to search the catalog](https://catalog.caida.org/recipe/how_to_search_the_catalog) under the search bar on all pages.  We created DOIs for all ongoing datasets and will propagate those into the catalog citation.  As the amount of data grew, we also took time to refactor and improve the load time of our search pages.  We created a [feedback page](https://catalog.caida.org/feedback) to solicit feedback on the catalog design or on a specific resource.

{{< clear-float both >}}

### Data Distribution Statistics  

{{< figure src="/about/annualreports/2023/images/user_downloads_by_as_and_country.png" width="350px" class="float-right" caption="Unique users downloading CAIDA data and corresponding ASes aggregated by country." >}}

CAIDA has been a trusted source of data and knowledge for the past twenty-five years, playing a crucial role in advancing research on critical Internet infrastructure. The field of Internet research heavily relies on CAIDA's robust measurement and data sharing infrastructure. CAIDA has shared data and knowledge, including sensitive knowledge about critical Internet infrastructure, for over quarter of a century. The field of Internet infrastructure research is essentially dependent on CAIDA’s measurement and data sharing infrastructure. CAIDA’s data enables organizations to identify and remediate various Internet transport layers vulnerabilities including IP spoofing, BGP routing attacks, DNS abuse, and Certificate Authority manipulations.

To facilitate seamless access to its valuable resources, CAIDA employs multiple data sharing methods. These methods encompass downloadable files, interactive Web services, programmatic access to data streams, and APIs. 

Users now request access to CAIDA's data through the [CAIDA Resource Catalog](https://catalog.caida.org/search?query=types=dataset%20caida).  CAIDA datasets fall into two categories: public and by-request.  We make public datasets available to users who agree to [CAIDA's Acceptable Use Policy for public data](/about/legal/aua/public_aua/).  We  safeguard restricted datasets and make them available for use by academic researchers, U.S. government agencies, and corporate entities through the UC San Diego's Office of Innovation and Commercialization. Users fill out the appropriate request form including a brief description of their intended use of the data, and agree to an [Acceptable Use Policy](/about/legal/aua/).  

<!-- Requires Review -->
In the following graphs, an unique user is defined as an unique IP address that has accessed restricted or publicly available datasets and services. We have notably made efforts in filtering potential bots, crawlers and spiders from listed totals. The totals reported in this year’s report reflects more accurate accounts of usage than previous years, where numbers may have been inflated due to previously uncaught spiders and scanners.

{{< figure src="/about/annualreports/2023/images/total_unique_users_by_dataset.png" width="300px" class="float-right print-wide" caption="Data Distribution Statistics: Unique users downloading CAIDA data downloaded annually. Top 10 Datasets in 2023.">}}

<!-- TODO lp Update after confirming numbers-->
{{< figure src="/about/annualreports/2023/images/total_unique_users_by_dataset_year.png" width="300px" class="float-right print-wide" caption="Data Distribution Statistics: Unique users downloading CAIDA data downloaded annually. AS Rank and BGPStream unique users were calculated based on API access." >}}

<!-- Requires Review -->
The Data Distribution Statistics (bar & pie) graphs show the top highly used datasets and their annual count of unique visitors who downloaded CAIDA datasets (public and by-request) over time and of 2023 respectively. These statistics do not include Near-Real-Time Telescope datasets (raw traffic traces in pcap format, aggregated flow and daily RSDoS attack metadata).

<!-- Requires Review -->
As depicted in the Data Distribution Statistics Bar graph, there was a surge in the number of unique users accessing AS-Rank, Anonymized Internet Traces, Ark Topology, and Routeviews Prefix2as in the years 2020 and 2021, and upon investigating, we identified the cause to be an influx of IP addresses originating from specific ASes, namely Amazon (Hosting), CHINA UNICOM Industrial Internet Backbone, and China Telecom. These IP addresses were primarily making single requests, leading to the spikes observed during 2020 and 2021. The decline in the number of unique IPs from all four ASes over the subsequent years has contributed to the downward trend observed in the number of users accessing these datasets.
 
Our most popular publicly available datasets are ongoing ["Routviews Prefix to AS Mapping"](https://catalog.caida.org/dataset/routeviews_ipv4_prefix2as), ["BGPStream"](https://catalog.caida.org/software/bgpstream) and 2019-2021 [Hoiho papers data supplements](https://catalog.caida.org/search?query=types%3Dpaper%20links%3Dtag%3Acaida%20hoiho).

In 2023 users downloaded about 70 TB of data. The main data categories contributing to the volume of downloaded data are: Anonymized Internet Passive Traces (24 TB) and Ark Topology data (42 TB).

{{< figure src="/about/annualreports/2023/images/grand_total_downloads.png" width="300px" class="float-right print-wide" caption="Total downloads (GB) of CAIDA data across two decades." >}}

{{< figure src="/about/annualreports/2023/images/grand_total_unique_users.png" width="300px" class="float-right print-wide" caption="Total unique users of CAIDA data across two decades." >}}

<!-- Requires Review -->
In sharing data for close to two decades, CAIDA has served and serviced terabytes of data and thousands of users respectively. The total downloads and users graphs depict the increasing usage of CAIDA’s datasets and services over time, cementing the credibility and notoriety of CAIDA’s crucial role in advancing research within the Internet research community.

<!-- {{< figure src="/about/annualreports/2022/images/data_downloads.png" width="600px" class="float-left print-wide" caption="Data Distribution Statistics: Volume of data downloaded annually. Multiple downloads of the same file by the same user, which is common, only counted once." >}} --> 


{{< clear-float >}}

[AS Rank]: # (==================================================================================================)
### AS Rank usage statistics

{{< figure src="/about/annualreports/2023/images/asrank_number_of_requests_by_country_2020_2021_2022_2023.png" width="293px" class="float-right" caption="AS Rank requests received annually aggregated by country." >}}

{{< figure src="/about/annualreports/2023/images/asrank_number_of_requests_by_org_type_2020_2021_2022_2023.png" width="300px" class="float-right" caption="AS Rank requests received annually aggregated by organization type." >}}

In 2023, over 196 ASes from U.S. Education and Research Groups have
utilized AS Rank, alongside 39 ASes from U.S. Government and Public
Administration Groups. Across the past four years, Nonprofit, Education
and Government institutions have steadily increased their usage of AS Rank
services, showcasing AS Rank’s popularity amongst different organizations.

{{< clear-float >}}

### BGPstream

{{< figure src="/about/annualreports/2023/images/bgpstream_number_of_requests_by_country.png" width="300px" class="float-right" caption="BGPstream requests received annually aggregated by country." >}}

{{< figure src="/about/annualreports/2023/images/bgpstream_number_of_requests_by_org_type.png" width="330px" class="float-right" caption="BGPstream requests received annually aggregated by organization type." >}}

BGPStream usage has grown steadily over the last 3 years.
In 2023, there were 5,356 unique IPs sending requests to [BGPStream](https://bgpstream.caida.org/),
from 979 unique ASes in 95 countries, the top being US, China, Germany and the United Kingdom.
Of these unique IPs, at least 432 were from the research and education community, 303 of those in the U.S.

<!-- Most of these requests originated from organizations that span various industries such as Computer and Information Technology, Education and Research, Community Groups and Nonprofits, and more. With further analysis, requests originate from over 104 countries, the top being the US, France, China and Japan. In terms of use within the Education and Research Community, 329 unique IPs have sent requests, with 220 of those IPs being within the United States. --> 

<!-- Over the past three years, the usage of BGPStream has increased steadily as depicted in the graphs below. With growing usage within Community and Nonprofit, Computer and Information Technology, and Government and Public Administration groups. --> 

<!-- {{< figure src="/about/annualreports/2022/images/bgpstream-number-of-requests-by-year.jpg" width="300px" class="float-left" caption="Requests per year via the BGPstream API." >}} --> 

{{< clear-float >}}

### Publications using public and/or restricted CAIDA data (by non-CAIDA authors)
Users of CAIDA datasets agree, as part of the Acceptable Use Agreements (see "Data Distribution Statistics" section), to provide CAIDA with information of their publications using CAIDA data. Our Data Publication Report Page provides instructions on how to report papers most easily.

In addition, we are conducting extensive literature search trying to locate relevant papers. To initiate this process, we employ Google Scholar, utilizing search phrases derived from the names of CAIDA datasets. Our search strategy aligns with the reference format specified in the AUA. Notably, this approach yields the highest number of search results. To complement the outcomes from Google Scholar, we also utilize other search engines that have a stronger focus on computer science, such as IEEE Xplore Digital Library, ACM Digital Library, ScienceDirect.com, and Springer, among others. Although these targeted searches do not yield a significant number of additional hits compared to Google Scholar (approximately 5-15% of the total), they do reveal papers pertinent to subjects that extend beyond the domain of computer science.

We are aware of 128 publications authored by non-CAIDA researchers that utilized CAIDA data and that were published in 2023. Our external publications database is continuously updated as we become aware of new publications. As of today, we have indexed 3535 papers in our database.

Please let us know if you know of a paper using CAIDA data not yet on our list: [Non-CAIDA Publications using CAIDA Data](https://catalog.caida.org/search?query=types=paper%20!links=tag:caida%20links=tag:used_caida_data). 

{{< figure src="/about/annualreports/2023/images/papers_by_dataset_annual.png" width="300px" class="float-left print-wide" caption="Annual number of non-CAIDA publications using CAIDA data (lower bound)">}}

{{< figure src="/about/annualreports/2023/images/authors_by_country_annual.png" width="300px" class="float-left print-wide"  caption="Country of affiliation of authors of non-CAIDA papers using CAIDA data." >}}

{{< clear-float >}}

[BGPstream]: # (==================================================================================================)

[WORKSHOPS section]: # (==================================================================================================)
## Workshops

We continued to conduct monthly GMI-DDoS workgroup meetings involving academic and industry researchers. During these meetings, we made progress on the collaborative DDoS white paper aiming to compile insights from both industry and academia: documenting DDoS trends, related vulnerabilities, and mitigation strategies to tackle DDoS-related security challenges.

During the week of May 1-5, 2023 CAIDA hosted an in-person GMI-AIMS workshop, where we discussed active measurement needs of the community as we planned for the future of Ark, FANTAIL and other Internet measurement infrastructure.  A followup GMI-AIMS-2 community workshop was held October 30-November 3, also discussing the future of the 5G ecosystem as well as how to enhance and sustain the utility of the telescope data for a wider variety of users, including commercial users. 

{{< clear-float >}}

[CAIDA IN NUMBERS section]: # (==================================================================================================)
## CAIDA in Numbers
In 2023, CAIDA published 11 peer-reviewed papers (see below), made 22 presentations, and posted 5 blog entries. A list of presented materials is listed on the [CAIDA Resource Catalog](https://catalog.caida.org/search?query=types=media%20links=tag:caida).  Our web site www.caida.org attracted approximately 261,770 unique visitors, with an average of 1.84 visits per visitor, serving an average of 3.13 pages per visit.  During 2023, CAIDA employed {{< list/staff-count year="2023" type="staff" >}} staff (researchers, programmers, data administrators, technical support staff), hosted {{< list/staff-count year="2023" type="postdoc" >}} postdocs, {{< list/staff-count year="2023" type="phdStudent" >}} PhD students, {{< list/staff-count year="2023" type="mastersStudent" >}} masters students, and {{< list/staff-count year="2023" type="undergradStudent" >}} undergraduate students.

The chart below shows CAIDA operating expenses, with a breakdown of operating expenses by type and program area: 
{{< figure src="/about/annualreports/2023/images/operating_expenses_2023.png" width="750px" class="piechart print-wide" >}}

{{< add-to-next tag="table" class="ardata" >}}
| Expense type | Amount ($) | Percentage |
| --- | --- | --- |
| Labor | $1,669,395  | 37%|
| (UCSD) Indirect Costs | $1,368,653 | 30% |
| (UCSD) Benefits | $554,749 | 12%|
| Supplies & Expenses | $472,142 | 10%|
| Subcontracts | $321,307 | 7%|
| Equipment | $106,633  | 2%|
| Professional Development | $5,821 | <1%|
| Total | $4,498,700 | 100% |


<!-- omitted since 2022
{< figure src="/about/annualreports/2022/images/expenses_byfundingsource_2022.png" width="750px" class="piechart print-wide" >}

{< add-to-next tag="table" class="ardata" >}
| Funding Source | Amount ($) | Percentage |
| --- | --- | --- |
| NSF | $3,553,260 | 96%|
| Gift | $78,066| 2%|
| Other | $59,437 | 2%|
| Total | $3,690,763 |100%|

--> 

<!-- omitted since 2022
{{< figure src="/about/annualreports/2023/images/expenses_byprogram_2023.png" width="750px" class="piechart print-wide" >}}

-->



{{< add-to-next tag="table" class="ardata" >}}
| Research Program Area | Amount ($) | Percentage |
| --- | --- | --- |
| Infrastructure & Data Sharing |  $2,214,412 | 49%|
| Security, Stability, Resilience | $1,387,854 | 31% |
| Cartography | $611,701|  14%|
| Performance |  $284,732 |  6%|
| Total | $4,498,699 |100%|

{{< figure src="/about/annualreports/2023/images/funding_over_time_2023.png" width="500px" class="piechart float-left print-wide" >}}

<!-- omitted since 2022, but still used for funding page
{{< figure src="/about/annualreports/2023/images/funding_over_time_perc_2023.png" width="500px" class="piechart float-left print-wide" >}}
-->

{{< clear-float >}}

[PUBLICATIONS section]: # (==================================================================================================)
## Publications
Publications are grouped by research categories. 


### Network Measurement and Analysis
{{< add-to-next tag="ul" class="papers-byyear" >}}
* [Internet Science Moonshot: Expanding BGP Data Horizons](https://catalog.caida.org/details/paper/2023_internet_science_moonshot/), 22nd ACM Workshop, Nov 2023
* [IRRegularities in the Internet Routing Registry](https://catalog.caida.org/details/paper/2023_irregularities_in_internet_routing_registry/), ACM Internet Measurement Conference (IMC), Oct 2023
* [Coarse-grained Inference of BGP Community Intent](https://catalog.caida.org/details/paper/2023_coarse_grained_inference_bgp/), ACM Internet Measurement Conference (IMC), Oct 2023
* [Empirically Testing the PacketLab Model](https://catalog.caida.org/details/paper/2023_empirically_testing_packetlab_model/), ACM Internet Measurement Conference (IMC), Oct 2023
* [Taking the Low Road: How RPKI Invalids Propagate](https://catalog.caida.org/details/paper/2023_taking_low_road/), ACM SIGCOMM Poster, Sep 2023

### Internet Routing and Security
{{< add-to-next tag="ul" class="papers-byyear" >}}
* [On the Importance of Being an AS: An Approach to Country-Level AS Rankings](https://catalog.caida.org/details/paper/2023_on_importance_being_as/), ACM Internet Measurement Conference (IMC), Oct 2023
* [A path forward: Improving Internet routing security by enabling trust zones](https://catalog.caida.org/details/paper/2023_a_path_forward/), Jul 2023
* [Access Denied: Assessing Physical Risks to Internet Access Networks](https://catalog.caida.org/details/paper/2023_access_denied/), USENIX Security Symposium, Aug 2023

### Legal and Regulatory Impact
{{< add-to-next tag="ul" class="papers-byyear" >}}
* [Notice of Ex Parte Meeting, Secure Internet Routing](https://catalog.caida.org/details/paper/2023_notice_of_ex_parte_meeting_fcc_22_90/), Jan 2023
* [The EU Digital Services Act and Academic Research - Technical Report](https://catalog.caida.org/details/paper/2023_eu_digital_services_act/), Aug 2023

### Data and Ontology Mapping
{{< add-to-next tag="ul" class="papers-byyear" >}}
* [Annotated Schema: Mapping Ontologies onto Dataset Schemas](https://catalog.caida.org/details/paper/2023_annotated_schema/), May 2023


[SUPPORTING RESOURCES section]: # (==================================================================================================)
## Supporting Resources 
CAIDA's accomplishments are in large measure due to the high quality of our visiting students and collaborators. We are also fortunate to have financial and IT support from sponsors, members, and collaborators, and monitoring hosting sites.
In 2022 we welcomed Matthew Luckie (who was a visiting scholar in the first half of the year) and Brendon Jones as consulting research scientists to advise on and execute our infrastructure deployment efforts.


### UC San Diego Graduate Students
{{< list/staff-byyear year="2023" type="ucsd" >}}

### Visiting Scholars
{{< list/staff-byyear year="2023" type="vs" >}}

### Funding Sources  

{{< list/funding-byyear year="2023" >}} 
