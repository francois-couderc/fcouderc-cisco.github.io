# IPs and credentials

## Switches

| Device   | SSH access        | Private IP      | Login | Password | Console (telnet) |
| -------- | ----------------- | --------------- | ----- | -------- | ---------------- |
| Leaf-111 | 10.60.9.123 10111 | 192.168.123.111 | admin | cisco123 | 10.60.9.123 2071 |
| Leaf-112 | 10.60.9.123 10112 | 192.168.123.112 | admin | cisco123 | 10.60.9.123 2072 |
| Leaf-113 | 10.60.9.123 10115 | 192.168.123.115 | admin | cisco123 | 10.60.9.123 2079 |
| Spine-11 | 10.60.9.123 10121 | 192.168.123.121 | admin | cisco123 | 10.60.9.123 2069 |
| Spine-12 | 10.60.9.123 10122 | 192.168.123.122 | admin | cisco123 | 10.60.9.123 2070 |
| Core-1   | 10.60.9.123 10119 | 192.168.123.119 | admin | cisco123 | 10.60.9.123 2067 |
| Core-2   | 10.60.9.123 10120 | 192.168.123.120 | admin | cisco123 | 10.60.9.123 2068 |
| Leaf-121 | 10.60.9.123 10113 | 192.168.123.113 | admin | cisco123 | 10.60.9.123 2073 |
| Leaf-122 | 10.60.9.123 10114 | 192.168.123.114 | admin | cisco123 | 10.60.9.123 2074 |
| Leaf-123 | 10.60.9.123 10116 | 192.168.123.116 | admin | cisco123 | 10.60.9.123 2076 |
| Spine-21 | 10.60.9.123 10123 | 192.168.123.123 | admin | cisco123 | 10.60.9.123 2075 |

## APICs

| Device | SSH access  | Private IP      | Login | Password | CIMC access       | Private IP      | Login | Password |
| :----- | :---------- | --------------- | ----- | -------- | ----------------- | --------------- | ----- | -------- |
| APIC-1 | 10.60.9.127 | 192.168.123.100 | admin | cisco123 | 10.60.9.123 20151 | 192.168.123.151 | admin | cisco123 |
| APIC-2 | 10.60.9.83  | 192.168.123.101 | admin | cisco123 | 10.60.9.123 20152 | 192.168.123.152 | admin | cisco123 |

## Nexus Dashboard physical cluster

| ND-1 (WMP250600S3) | Login | Password    | IP                | IPDG            | VLAN |
| ------------------ | ----- | ----------- | ----------------- | --------------- | ---- |
| CIMC               | admin | Cisco1234   | 192.168.123.73/24 | 192.168.123.254 |      |
| OOB                | admin | cisco123ND! | 192.168.123.76/24 | 192.168.123.254 |      |
| Inband             |       |             | 1.250.250.76/24   | 1.250.250.250   | 250  |

| ND-2 (WMP250600RU) | Login | Password    | IP                | IPDG             | VLAN |
| ------------------ | ----- | ----------- | ----------------- | ---------------- | ---- |
| CIMC               | admin | Cisco1234   | 192.168.123.74/24 | 192.168.123.254  |      |
| OOB                | admin | cisco123ND! | 192.168.123.77/24 | 192.168..123.254 |      |
| Inband             |       |             | 1.250.250.77/24   | 1.250.250.250    | 250  |

| ND-3 (WMP250600RD) | Login | Password    | IP                | IPDG             | VLAN |
| ------------------ | ----- | ----------- | ----------------- | ---------------- | ---- |
| CIMC               | admin | Cisco1234   | 192.168.123.75/24 | 192.168.123.254  |      |
| OOB                | admin | cisco123ND! | 192.168.123.78/24 | 192.168..123.254 |      |
| Inband             |       |             | 1.250.250.78/24   | 1.250.250.250    | 250  |

Data Service IPs : `1.250.250.101 -> 1.250.250.110`

Management Service IPs : `192.168.123.41 -> 192.168.123.47`

## VMware

### ESXs

| Device  | SSH access  | Private IP      | Login | Password  | CIMC access       | Private IP      | Login | Password |
| ------- | ----------- | --------------- | ----- | --------- | ----------------- | --------------- | ----- | -------- |
| ESX-OOB | 10.60.9.199 | 192.168.123.199 | root  | !Cisco123 | 10.60.9.123 20153 | 192.168.123.153 | admin | cisco123 |
| ESX-1   | 10.60.9.81  | 192.168.123.201 | root  | !Cisco123 | 10.60.9.123 20154 | 192.168.123.154 | admin | cisco123 |
| ESX-2   | 10.60.9.82  | 192.168.123.202 | root  | !Cisco123 | 10.60.9.123 20155 | 192.168.123.155 | admin | cisco123 |
| ESX-3   | 10.60.9.98  | 192.168.123.203 | root  | !Cisco123 | 10.60.9.123 20156 | 192.168.123.156 | admin | cisco123 |
| ESX-4   | 10.60.9.99  | 192.168.123.204 | root  | !Cisco123 | 10.60.9.123 20157 | 192.168.123.157 | admin | cisco123 |

### VMs

| VM      | Public access     | Private IP      | Login         | Password |
| ------- | ----------------- | --------------- | ------------- | -------- |
| vCenter | 10.60.9.146       | 192.168.123.200 | administrator | cisco123 |
| DNS     | 10.60.9.123 10005 | 192.168.123.5   | labuser       | cisco123 |
