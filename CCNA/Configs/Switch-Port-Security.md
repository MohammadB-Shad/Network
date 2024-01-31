# Switch Port Security 
- We will allow some MAC addresses to connect to the switch(This Sample 2 MAC).
- We will statically configure these 2 allowed MAC addresses.
- We will also set violation mode as shutdown.
  ```
  Sw(config)# interface fastEthernet 0/1
  Sw(config-if)# switchport mode access
  Sw(config-if)# switchport port-security
  Sw(config-if)# switchport port-security maximum 2
  Sw(config-if)# switchport port-security mac-address 11:11:11:11:11:11
  Sw(config-if)# switchport port-security mac-address 22:22:22:22:22:22
  Sw(config-if)# switchport port-security violation shutdown
  ```

