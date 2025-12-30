# Phase 1 - System planning and Distribution Selection ( week 1 )

## module: computer operating systems 


---

## Preface

This initial stage centers on mapping out the deployment and picking the right distributions for the environment. The core of the setup is a dual-system architecture: a headless Ubuntu Server managed entirely through SSH from a Windows 11 host. My primary goal here is to establish the remote connection and use command-line tools to document the base system specs before any further configuration begins.

the enviroment consist of a ** windows 11 workstation** hosting an ** ubuntu server vitual machine ** connected via a **Host-Only network**.

---

## 1. System Architechture Diagram

The diagram below shows the system architechtur, including the workstation,

![System Architecture Diagram](A.Diagram.drawio.png)

**Achitecture Summary:**
- Host OS: Windows 11 Workstation
- Hypervisor: Oracle VirtualBox
- Guest OS: Ubuntu server (VM)
- Network Type: Host-Only Network (vboxnet0)
- purpose: Secure Local Communication and SSH access between host and server VM

  ---

  ## 2. Distribution Selection Justification

  ### Selected Distribution: **Ubuntu Server**

  Ubuntu server was selected for the following reasons:
  - Long - term support (LST) release provide stability and security updates
  - Strong community support and documentation
  - Widely used in enterprise and cloud enviroments
  - Lightweight and efficient for server-base workloads
  - Excellent compatibility with security tools and services

    ### Comparision with Alternatives
    | Distribution | Reason Not Selected |
    |--------------|---------------------|
    | CentOS / Rocky Linux | more complex administration for beginners |
    | Debians | very stable but slower udpate cycle |
    | Fedora server | short support  lifecycle |
    | Arch Linux | Rolling release not ideal for stable servers |

    Ubuntu Server provides the best balance between **stability, usability, and industry relevance**.

    ---

    ## 3. Workstation Configuration Decision

     ### Selected Workstation: **Windows 11**

    The Windows 11 workstation was chosen because:
    - Native support for Virtualbox
    - Built-in OpenSSH client via PowerShell
    - Familiar user interface for development and administration
    - Supports cybersecurity tools and documentation workflows
    - Reliable for hosting virtualized lab enviroments

      ---

      ## 4. Network Configuration Documentation

      ### Virtual Network Settings
   
      ![System Architecture Diagram](B.image_networking.png)

      - Adapter Type: Host- Only Adapter
      - Network Name: vboxnet0
      - Purpose: Allow communication between host and VM without external internal exposure

        ### IP Addressing
     
        ![System Architecture Diagram](C.SERVER_IP_addr.png)

        - Ubuntu Server IP Address:  '192.168.56.103/24'
        - Network Range: '192.168.56.255'
        - Communicating method: SSH from Windows host to ubuntu server VM

          ### SHH Test (From Windows PowerShell)
       
          ![System Architecture Diagram](E.image.SSH2.png)

          ```Powershell
ssh alvan@192.168.56.101

---

## System Specifications (CLI Documentation)

**uname -a**

Shows the Linux kernel version, system architecture,and hostname.

![System Architecture Diagram](F.ServerUbuntu_UNAME.Png)

**free -h

Display total, used, and available Ram and exchange memory.

![System Architecture Diagram](H.FREE-H.png)

df -h

shows disk usage for all mounted filesystems, including available storage.

![System Architecture Diagram](l.SSH_DF-H.png)

IP addr
Gives all network interfaces and IP addresses, confirming the Host-Only IP used for SSH.

![System Architecture Diagram](D.IP_addr.png)

lsb_release -a

identifies the linux distribution and version(ubuntu server 22.04 LTS).



        

        
          

        
 

    
  












