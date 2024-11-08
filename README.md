# Network-Design_Mini-Project

## OVERIVIEW
This project outlines the network configuration for XYZ Engineering College, designed to optimize connectivity across the campus's 4 buildings having 6 departments, administration, library, and student labs. The network design includes separate networks for each department, administration, library and student labs, with an additional backbone area for establishing network connection among inter networks and with the networks outside of the organization. The student labs are further segmented into three VLANs to ensure efficient and secure data management across various academic and research activities.

![final](https://github.com/user-attachments/assets/5066df76-3f8a-4af4-889b-f92ccee09292)

## IP Addressing Scheme
- **Major Network IP Address**: 10.0.0.0/22
- **Available IP Addresses**: 1022
- **Number of IP Addresses Needed**: 540

## VARIABLE LENGTH SUBNETTING (VLSM)

| Subnet Name      | No. Of Hosts | Network ID       | Subnet Mask       | Assignable Range         | Broadcast   |
|------------------|--------------|------------------|-------------------|--------------------------|-------------|
| Students Labs    | 180          | 10.0.0.0/24      | 255.255.255.0     | 10.0.0.1 - 10.0.0.254    | 10.0.0.255 |
| Computer         | 96           | 10.0.1.0/25      | 255.255.255.128   | 10.0.1.1 - 10.0.1.126    | 10.0.1.127 |
| Library          | 50           | 10.0.1.128/26    | 255.255.255.192   | 10.0.1.129 - 10.0.1.190  | 10.0.1.191 |
| Electrical       | 48           | 10.0.1.192/26    | 255.255.255.192   | 10.0.1.193 - 10.0.1.254  | 10.0.1.255 |
| Administration   | 40           | 10.0.2.0/26      | 255.255.255.192   | 10.0.2.1 - 10.0.2.62     | 10.0.2.63  |
| Applied Science  | 24           | 10.0.2.64/27     | 255.255.255.224   | 10.0.2.65 - 10.0.2.94    | 10.0.2.95  |
| Architect        | 24           | 10.0.2.96/27     | 255.255.255.224   | 10.0.2.97 - 10.0.2.126   | 10.0.2.127 |
| Civil            | 24           | 10.0.2.128/27    | 255.255.255.224   | 10.0.2.129 - 10.0.2.158  | 10.0.2.159 |
| Mechanical       | 24           | 10.0.2.160/27    | 255.255.255.224   | 10.0.2.161 - 10.0.2.190  | 10.0.2.191 |
| Interface A      | 2            | 10.0.2.192/30    | 255.255.255.252   | 10.0.2.193 - 10.0.2.194  | 10.0.2.195 |
| Interface B      | 2            | 10.0.2.196/30    | 255.255.255.252   | 10.0.2.197 - 10.0.2.198  | 10.0.2.199 |
| Interface C      | 2            | 10.0.2.200/30    | 255.255.255.252   | 10.0.2.201 - 10.0.2.202  | 10.0.2.203 |
| Interface D      | 2            | 10.0.2.204/30    | 255.255.255.252   | 10.0.2.205 - 10.0.2.206  | 10.0.2.207 |
| Interface E      | 2            | 10.0.2.208/30    | 255.255.255.252   | 10.0.2.209 - 10.0.2.210  | 10.0.2.211 |
| Interface F      | 2            | 10.0.2.212/30    | 255.255.255.252   | 10.0.2.213 - 10.0.2.214  | 10.0.2.215 |
| Interface G      | 2            | 10.0.2.216/30    | 255.255.255.252   | 10.0.2.217 - 10.0.2.218  | 10.0.2.219 |
| Interface H      | 2            | 10.0.2.220/30    | 255.255.255.252   | 10.0.2.221 - 10.0.2.222  | 10.0.2.223 |
| Interface I      | 2            | 10.0.2.224/30    | 255.255.255.252   | 10.0.2.225 - 10.0.2.226  | 10.0.2.227 |
| Interface J      | 2            | 10.0.2.228/30    | 255.255.255.252   | 10.0.2.229 - 10.0.2.230  | 10.0.2.231 |
| Interface K      | 2            | 10.0.2.232/30    | 255.255.255.252   | 10.0.2.233 - 10.0.2.234  | 10.0.2.235 |
| Interface L      | 2            | 10.0.2.236/30    | 255.255.255.252   | 10.0.2.237 - 10.0.2.238  | 10.0.2.239 |
| Interface M      | 2            | 10.0.2.240/30    | 255.255.255.252   | 10.0.2.241 - 10.0.2.242  | 10.0.2.243 |
| Interface N      | 2            | 10.0.2.244/30    | 255.255.255.252   | 10.0.2.245 - 10.0.2.246  | 10.0.2.247 |
| Interface O      | 2            | 10.0.2.248/30    | 255.255.255.252   | 10.0.2.249 - 10.0.2.250  | 10.0.2.251 |
| Interface P      | 2            | 10.0.2.252/30    | 255.255.255.252   | 10.0.2.253 - 10.0.2.254  | 10.0.2.255 |

## VLAN CONFIGURATION
Here, the network "Student Labs" is subdivided to create three VLANs, resulting in the subnetting of the network ID 10.0.0.0/24 into three separate subnetted VLANs.

| Vlan Name                | No. Of Hosts | Network Id      | Subnet Mask       | Assignable Range                | Broadcast    |
|--------------------------|--------------|-----------------|-------------------|---------------------------------|--------------|
| Vlan 1 [Students- Lab1]  | 60           | 10.0.0.0/26     | 255.255.255.192   | 10.0.0.1 - 10.0.0.62            | 10.0.0.63    |
| Vlan 2 [Students- Lab2]  | 60           | 10.0.0.64/26    | 255.255.255.192   | 10.0.0.65 - 10.0.0.126          | 10.0.0.127   |
| Vlan 3 [Students- Lab3]  | 60           | 10.0.0.128/26   | 255.255.255.192   | 10.0.0.129 - 10.0.0.190         | 10.0.0.191   |

## OSPF CONFIGURATION
Here, each building is treated as one area of OSPF, i.e area-1 to area-4. The backbone area(or area 0) helps to route the packets among different areas.

| AREA ID     | BUILDING        | DEPARTMENTS                                       | ROUTERS                                                                                                                  |
|-------------|-----------------|---------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| AREA 1      | BUILDING - D    | Students Labs, Library, Administration            | Student_Labs Router [Router 1], Library Router [Router 2], Administration Router [Router 3]                              |
| AREA 2      | BUILDING - C    | Mechanical Department, Applied Science Department | Mechanical_Dept Router [Router 5], Applied_Science Router [Router 6]                                                     |
| AREA 3      | BUILDING - B    | Civil Department, Architect Department            | Civil_Dept Router [Router 8], Architect_Dept Router [Router 9]                                                           |
| AREA 4      | BUILDING - A    | Computer Department, Electrical Department        | Computer_Dept Router [Router 11], Electrical_Dept Router [Router 12]                                                     |
| AREA 0      | -               | -                                                 | Main Campus Router [Router 14]                                                                                           |
| AREA BORDER | -               | -                                                 | Building-D Router [Router 4], Building-C Router [Router 7], Building-B Router [Router 10], Building-A Router [Router 13] |

## WEB AND DNS SERVER CONFIGURATION
Here, I have configured two web servers and two dns server located at different network area.

| WEB/DNS | URL/NAME        | IP ADDRESS   | NETWORK               |
|---------|-----------------|--------------|-----------------------|
| WEB     | cisco.com       | 10.0.1.195   | Electrical Department |
| WEB     | intro.com       | 10.0.2.4     | Administration        |
| DNS     | DNS Server 1    | 10.0.2.3     | Administration        |
| DNS     | DNS Server 2    | 10.0.1.4     | Computer Department   |

## DHCP SERVER CONFIGURATION
The DHCP Servers have been configured inside two different networks.

| DHCP Name        | Router                | IP Pool       | Gateway    | DNS Server |
|------------------|-----------------------|---------------|------------|------------|
| civil_dept       | Civil_Dept Router     | 10.0.2.128/27 | 10.0.2.129 | 10.0.2.3   |
| architect_dept   | Architect_Dept Router | 10.0.2.96/27  | 10.0.2.97  | 10.0.1.4   |

## ADDITIONAL CONFIGURATION
The paragraph describes the additional configurations implemented in the network design project as follows:
- OSPF routing protocol is employed for internal routing. Any ping request to the devices outside the network is directed to the ISP Router. This is achieved by configuring a default route within the main-campus router, which is subsequently distributed within the OSPF network.
- The ISP router is configured with a Static Route to facilitate the forwarding of all network packets to the XYZ-Engineering network.
- Building-C and Building-A have been equipped with multiple paths, aligning with the specifications outlined in the proposal requirements.

## ROUTER PASSWORD CONFIGURATION
The router password configuration is as below:
- Password for privileged access mode: `class`
- Password for console line: `cisco`
- Password for virtual terminal (telnet): `cisco`

## CONCLUSION
To sum things up, the network project for XYZ-Engineering College reflects a comprehensive solution tailored to the institution's networking needs. I employed Variable Length Subnetting (VLSM) to effectively manage IP addresses, facilitating the coexistence of various departments and segments within the major network. The segmentation of the "Student Labs" network into VLANs enhances both network security and management. Utilizing the OSPF routing protocol with distinct areas optimizes packet routing and communication. 

Furthermore, strategically situating web and DNS servers across diverse network zones improves service availability and load distribution. The implementation of DHCP servers in different network sections streamlines the management of IP addresses, simplifying the provisioning of network devices. Lastly, additional configurations such as OSPF routing, setting up static routes for the ISP underscore my commitment to enhancing resilience, fault tolerance, and efficient data flow within the project. To conclude, the network design project showcases meticulous planning, effective application of networking principles, and my dedication to meeting the connectivity and resource requirements of XYZ-Engineering College.


