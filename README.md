# ICS3_Network_Project

Réseaux inter-routeur : 192.168.0.0/24

| Connection | Nombre d'hôte | Pas | Masque (/) | Masque décimal | Adresse réseau | Adresse de diffusion |
|------------|---------------|-----|------------|----------------|----------------|----------------------|
| R1-R2      |   2           | 2^2 | 32 -2 = /30| 255.255.255.252| 192.168.0.0    | 192.168.0.3          |
| R2-R3      |   2           | 2^2 | 32 -2 = /30| 255.255.255.252| 192.168.0.4    | 192.168.0.7          |
| R3-R1      |   2           | 2^2 | 32 -2 = /30| 255.255.255.252| 192.168.0.8    | 192.168.0.11         |

Réseau : 172.22.148.0/22

255.255.1111 1100.0 ==> 255.255.252.0

| VLAN | Nombre d'hôte | Pas | Masque (/) | Masque décimal | Adresse réseau | Adresse de diffusion |
|------|---------------|-----|------------|----------------|----------------|----------------------|
| 50   |   500         | 2^9 | 32 -9 = /23| 255.255.254.0  | 172.22.148.0   | 172.22.149.255       |
| 40   |   120         | 2^7 | 32 -7 = /25| 255.255.255.128| 172.22.150.0   | 172.22.150.127       |
| 30   |   30          | 2^5 | 32 -5 = /27| 255.255.255.224| 172.22.150.128 | 172.22.150.159       |
| 20   |   12          | 2^4 | 32 -4 = /28| 255.255.255.240| 172.22.150.160 | 172.22.150.175       |
| 10   |   4           | 2^3 | 32 -3 = /29| 255.255.255.248| 172.22.150.176 | 172.22.150.183       |

Serveur DNS : 172.22.150.161

Serveur Web : 172.22.150.162

Les adresses IPv4 des passerelles sont les dernières IPv4 utilisables dans chaque réseaux.
# Justification
## VLAN 50 

Besoin : 500 adresses IPv4.

### Nombre de bits nécessaire :

`2^?-2 >= 500`

`2^9-2 = 510 adresses disponibles`

### Calcul du masque :
`32-9 = 23`

`255.255.1111 1110.0 ==> 255.255.254.0`

### Adresse réseau :
`172.22.148.0`

### Adresse de diffusion :
`172.22.1001 010|1.1111 1111 ==> 172.22.149.255`

## VLAN 40 

Besoin : 120 adresses IPv4.

### Nombre de bits nécessaire :

`2^?-2 >= 120`

`2^7-2 = 126 adresses disponibles`

### Calcul du masque :
`32-7 = 25`

`255.255.1111 1111.1000 0000 ==> 255.255.255.128`

### Adresse réseau :
`172.22.150.0`

### Adresse de diffusion :
`172.22.1001 0110.0|111 1111 ==> 172.22.150.127`

## VLAN 30 

Besoin : 30 adresses IPv4.

### Nombre de bits nécessaire :

`2^?-2 >= 30`

`2^5-2 = 30 adresses disponibles`

### Calcul du masque :
`32-5 = 27`

`255.255.1111 1111.1110 0000 ==> 255.255.255.224`

### Adresse réseau :
`172.22.150.128`

### Adresse de diffusion :
`172.22.1001 0110.100|1 1111 ==> 172.22.150.159`

## VLAN 20 

Besoin : 12 adresses IPv4.

### Nombre de bits nécessaire :

`2^?-2 >= 12`

`2^4-2 = 14 adresses disponibles`

### Calcul du masque :
`32-4 = 28`

`255.255.1111 1111.1111 0000 ==> 255.255.255.240`

### Adresse réseau :
`172.22.150.160`

### Adresse de diffusion :
`172.22.1001 0110.1010| 1111 ==> 172.22.150.175`

## VLAN 10 

Besoin : 4 adresses IPv4.

### Nombre de bits nécessaire :

`2^?-2 >= 4`

`2^3-2 = 6 adresses disponibles`

### Calcul du masque :
`32-3 = 29`

`255.255.1111 1111.1111 1000 ==> 255.255.255.248`

### Adresse réseau :
`172.22.150.176`

### Adresse de diffusion :
`172.22.1001 0110.1011 0|111 ==> 172.22.150.183`