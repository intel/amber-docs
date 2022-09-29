# Client Integration
This page describes the suggested requirements for each customer solution.
As the number of PoC solutions grows and more details are gathered, the following items will be adapted and refined accordingly.
## 1. Native SGX SDK PoC
### Applicable scenarios:S
- Customer has knowledges of confidential computing, and has the capability of developing TEE applications based on Intel SGX-SDK. 
- Customer does not have enough knowledge on TEE trust application development, but is comfortable to share source code.<br>
- The source code is written in SGX friendly language families. e.g., C/C++.S
### Hardware requirement:
SGX2 enabled server (ICX)
Production platform and can be recognized by PCS
https://github.com/intel/SGXDataCenterAttestationPrimitives/blob/master/QuoteGeneration/pccs/README.md
### Software requirements:S
**Supported Software stack:**
- Linux Kernel 5.11 and onwards (with in-tree kernel)
- Intel SGX SDK for Linux OS
- Intel SGX DCAP
- Amber client SDKs if applicable
- https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/linux-overview.html#downloads
### System requirements:
**Supported Linux based OSes:**
centos-stream
rhel8.4-server
ubuntu18.04-server
ubuntu20.04-server
Network requirements:
Amber SaaS reachable network connection
## 2. Native TDX PoC
T.B.D.
## 3. Graminized SGX PoC
### Applicable scenarios:
- Customer does not have enough knowledge on TEE trust application development, and is unable to share source code but only binaries
- Customer can share the source code, but code core logics are not written in C/C++ and can not integrated with Intel SGX SDK API
### Hardware requirement:
- SGX2 enabled server
- Production platform and can be recognized by PCS
https://github.com/intel/SGXDataCenterAttestationPrimitives/blob/master/QuoteGeneration/pccs/README.md
### Software requirements:
**Supported Software stack:**
- Linux Kernel 5.11 and onwards (with in-tree kernel)
- Intel SGX SDK for Linux OS
Intel SGX DCAP
https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/linux-overview.html#downloads
**Supported system C libraries:**
- Glibc, version 2.35
- Musl, version 1.2.2
### System requirements:
**upported Linux based OSes:**
- Ubuntu 18.04
- Ubuntu 20.04
- RHEL-8-like distribution (like AlmaLinux 8, CentOS 8, Rocky Linux 8, …)
https://gramine.readthedocs.io/en/stable/quickstart.html#install-gramine
### Network requirements:
- Amber SaaS reachable network connection
### Gramine-SGX limitations:
- Gramine v1.2 (latest stable version)
- Netlink protocol is not well supported
- Not all syscalls have been implemented by Gramine LibOS (~40)
- Golang support is not stable
- It is unsecure for workloads (binary, libs) containing syscall instructions
- Performance overheads might be significant on some workloads (e.g. IO intensive WLs.)
## 4. Gramine -SGX GSC PoC (Containerized PoC)
### Applicable scenarios:
- Customer does not have enough knowledge on TEE trust application development, and is unable to share source code but only binaries
- Customer can share the source code, but code core logics are not written in C/C++ and can not integrated with Intel SGX SDK API
- Customer service logics require multiple components that differs on their dependencies 
### Hardware requirement:
- SGX2 enabled server
- Production platform and can be recognized by PCS
https://github.com/intel/SGXDataCenterAttestationPrimitives/blob/master/QuoteGeneration/pccs/README.md
### Software requirements:
- Native Gramine, and its related dependencies (as shown in #3)
Docker
### System requirements:
**Supported Docker container Linux based OSes:**
- - Ubuntu 18.04
Ubuntu 20.04
- Ubuntu 21.04
- CentOS 8
https://gramine.readthedocs.io/projects/gsc/en/latest/index.html?highlight=gsc#configuration
### Network requirements:
- Amber SaaS reachable network connection
### Other limitations
- https://gramine.readthedocs.io/projects/gsc/en/latest/index.html?highlight=gsc#limitations
## 5. Amber Client SDK PoC
### Applicable scenarios:
- Customer has knowledges of confidential computing, and has the capability of developing TEE applications based on Intel SGX-SDK. 
- Customer does not have enough knowledge on TEE trust application development, but is comfortable to share source code.
The source code is written in supported programming languages to which Amber client dev. SDK target
## SGX client SDKs
T.B.D
## TDX client SDKs
T.B.D
### Hardware requirement:
_ SGX2 enabled server
- Production platform and can be recognized by PCS
https://github.com/intel/SGXDataCenterAttestationPrimitives/blob/master/QuoteGeneration/pccs/README.md
### Network requirements:
- Amber SaaS reachable network connection
## 6. Others
We may extend our support for other Linux distro/version with extended development and adaption work. However, it required additional efforts/time, and the results are not guaranteed. For a quick PoC, demo or evaluation, we strongly suggest considering options listed above to start with

## 7. OS Supported by core dependent components
|Dependencies     |OS Supported       |
|-----------------|-------------------|
|Gramine          |Ubuntu 18.04 & 20.04<br> RHEL-8 like distribution<br> CentOS 8 <br> Debian 11    |
|DCAP Libraries   |Ubuntu 18.04 & 20.04<br>  RHEL 8.x<br>  CentOS Stream 8    |