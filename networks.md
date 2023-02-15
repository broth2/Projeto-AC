# IP subnetting

| Router 1     | Router 2     | interface     | ip                        |
| : ---------- | : ---------- | :-----------: | : --------------- :       |
| Porto        | Aveiro       |               | 10.0.1.1  255.255.255.192 |
| Porto        | Coimbra      |               | 10.0.1.2  255.255.255.192 |
| Porto        | P1           |               | 10.0.1.9  255.255.255.192 |
| Porto        | P2           |               | 10.0.1.10 255.255.255.192 |
| Lisboa       | Coimbra      |               | 10.0.1.3  255.255.255.192 |
| Lisboa       | L1           |               | 10.0.1.11 255.255.255.192 |
| Coimbra      | Porto        |               | 10.0.1.4  255.255.255.192 |
| Coimbra      | Aveiro       |               | 10.0.1.5  255.255.255.192 |
| Coimbra      | Lisboa       |               | 10.0.1.6  255.255.255.192 |
| Coimbra      | C1           |               | 10.0.1.12 255.255.255.192 |
| Aveiro       | A1           |               | 10.0.1.13 255.255.255.192 |
| Aveiro       | A2           |               | 10.0.1.14 255.255.255.192 |
| Aveiro       | Porto        |               | 10.0.1.7  255.255.255.192 |
| Aveiro       | Coimbra      |               | 10.0.1.8  255.255.255.192 |
| P1           | ---          | Lo0           | 10.0.1.66 255.255.255.255 |
| P2           | ---          | Lo0           | 10.0.1.67 255.255.255.255 |
| A1           | ---          | Lo0           | 10.0.1.68 255.255.255.255 |
| A2           | ---          | Lo0           | 10.0.1.69 255.255.255.255 |
| C1           | ---          | Lo0           | 10.0.1.70 255.255.255.255 |
| L1           | ---          | Lo0           | 10.0.1.71 255.255.255.255 |

| Subnet ID | Subnet Address | Host Address Range      | Broadcast Address | DataCenter |
| 1         | 10.0.0.0       | 10.0.0.1 - 10.0.0.62    | 10.0.0.63         | Porto      |
| 1.1       | 10.0.0.0       | 10.0.0.1 - 10.0.0.30    | 10.0.0.31         | Porto      |
| 1.2       | 10.0.0.32      | 10.0.0.33 - 10.0.0.62   | 10.0.0.63         | Porto      |
| 2         | 10.0.0.64      | 10.0.0.65 - 10.0.0.126  | 10.0.0.127        | Aveiro     |
| 2.1       | 10.0.0.64      | 10.0.0.65 - 10.0.0.94   | 10.0.0.95         | Aveiro     |
| 2.2       | 10.0.0.96      | 10.0.0.97 - 10.0.0.126  | 10.0.0.127        | Aveiro     |
| 3         | 10.0.0.128     | 10.0.0.129 - 10.0.0.190 | 10.0.0.191        | Lisboa     |
| 4         | 10.0.0.192     | 10.0.0.193 - 10.0.0.254 | 10.0.0.255        | Coimbra    |
| 5         | 10.0.1.0       | 10.0.1.1 - 10.0.1.62    | 10.0.1.63         | PN         |
| 5.1       | 10.0.1.0       | 10.0.1.1 - 10.0.1.15    | 10.0.1.15         | PN         |
| 5.2       | 10.0.1.16      | 10.0.1.17 - 10.0.1.30   | 10.0.1.31         | PN         |
| 5.3       | 10.0.1.32      | 10.0.1.33 - 10.0.1.46   | 10.0.1.47         | PN         |
| 5.4       | 10.0.1.48      | 10.0.1.49 - 10.0.1.62   | 10.0.1.63         | PN         |
| 6         | 10.0.1.64      | 10.0.1.65 - 10.0.1.126  | 10.0.1.127        | Loopbacks  |
| 7         | 10.0.1.128     | 10.0.1.129 - 10.0.1.190 | 10.0.1.191        | UNUSED     |
| 8         | 10.0.1.192     | 10.0.1.193 - 10.0.1.254 | 10.0.1.255        | UNUSED     |