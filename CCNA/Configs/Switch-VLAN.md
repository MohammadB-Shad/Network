# VLAN
- Virtual LAN is the logical grouping of network devices in the  same logical network, in same broadcast domain.
- Normally, these VLANs can not Communicate eachother. To do this they need a layer 3 device.(VLAN1 , VLAN2 , VLAN3)
    - Works on Layer 2
    - Used by switches
    - Used 4 Bytes VLAN ID to tag frames
    - Uses two port types: Access and Trunk
 
  # Access Ports
  - Configured to carry single VLAN traffic
  - Used to connect end devices, such as PCs, printers etc.
  - Easy to configure & troubleshoot
 
  # Trunk Ports
  - Used to carry traffic for multiple VLANs
  - Used to connect switches
  - Complex configure & troubleshoot
  - Ussed 802.1Q or ISL Encasplation
 
  # VLAN Ranges
  - VLAN 0, 4095: Reserved
  - VLAN 1: Default VLAN
  - VLAN 2-1001: Normal range
  - VLAN 1002-1005: Fddi and token rings
  - VALAN 1006-4094: Extended Range
 
  # VLAN Benefits
  - Improved network security
  - Better network performance
  - Simple Administration
  - Flexibility
  - Cost saving
  - Scalability
 
  # VLAN Attacks
  - CAM Table Overflow / MAC Attack
  - ARP Attack
  - Basic VLAN Hopping
  - Double Tagging VLAN Hopping Attack
  - VMPS / VQP Attack
 
# Configure VLANs
- Creating VLANs
  ```
  Switch (config)# vlan 2
  Switch (config-vlan)# name Team1
  Switch (config-vlan)# vlan 3
  Switch (config-vlan)# name Team2
  Switch (config-vlan)# vlan 4
  Switch (config-vlan)# name team3
  ```
- Setting Access Ports & Assigning VLANs
  ```
  Switch (config)# interface fa0/2
  Switch (config-if)# switchport mode access
  Switch (config-if)# switchport access vlan 2
  Switch (config-if)# interface fa0/3
  Switch (config-if)# switchport mode access
  Switch (config-if)# switchport access vlan 2
  Switch (config-if)# interface fa0/4
  Switch (config-if)# switchport mode access
  Switch (config-if)# switchport access vlan 3
  Switch (config-if)# interface fa0/5
  Switch (config-if)# switchport mode access
  Switch (config-if)# switchport access vlan 3
  Switch (config-if)# interface fa0/6
  Switch (config-if)# switchport mode access
  Switch (config-if)# switchport access vlan 4
  Switch (config-if)# interface fa0/7
  Switch (config-if)# switchport mode access
  Switch (config-if)# switchport access vlan 4
  ```
- Setting Trunk Interface
  ```
  Switch (config)# interface fa0/1
  Switch (config-if)# switchport mode trunk
  Switch (config-if)# switchport nonegotiate
  Switch (config-if)# switchport trunk encapsulation dot1.q
  Switch (config-if)# switchport trunk encapsulation nonegotiate
  ```
- Setting Native VLAN and Allowed VLANs
  ```
  Switch (config-if)# switchport trunk native vlan5
  Switch (config-if)# switchport trunk allowed valn all
  Switch (config-if)# switchport trunk allowed vlan 2,3,4,5
  ```
  
  
