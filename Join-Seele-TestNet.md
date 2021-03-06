# Join Seele TestNet

## Steps to join Seele Test Network  

_Notes: you should use the testnet1.1 branch for joining testNet.  `git checkout testnet1.1`_

### 1. Pick some seele test network nodes

Go to http://seelemonitor.net and select any Shard number in the left sidebar, then select any IP address from the NodeName (form: seele_node_ip) list. Replace the staticNodes field in node1.json with the new IP address. The file node1.json is located in `/go-seele/cmd/node/config/`

node1.json Fragment:
```json
··· ···
  "p2p": {
    "privateKey":"0xf65e40c6809643b25ce4df33153da2f3338876f181f83d2281c6ac4a987b1479",
    "staticNodes": ["ip:8057","ip1:8057"],
    "address": "0.0.0.0:8057",
    "networkID": 1
  }
··· ···
```

Each ip address in staticNodes should follow the "ip:port" format. If it is not just one, the format ["ip:port1", "ip:port2"...] should be followed.

In this step, all you have to do is change this line **_"staticNodes": ["ip:8057","ip1:8057"]_**.

### 2. Change the accounts.json
The file accounts.json is also located in `/go-seele/cmd/node/config/`

accounts.json:
```json
{
  "0x007d1b1ea335e8e4a74c0be781d828dc7db934b1": 1000000000000,
  "0x0a57a2714e193b7ac50475ce625f2dcfb483d741": 1000000000000,
  "0x2a23825407740fa7163069257c57452c4d4fc3d1": 1000000000000,
  "0x2a87b6504cd00af95a83b9887112016a2a991cf1": 1000000000000,
  "0x3b691130ec4166bfc9ec7240217fc8d08903cf21": 1000000000000,
  "0x4eea165e9266f20bf6e5e08e0c11d38e8fc02661": 1000000000000,
  "0x4fb7c8b0287378f0cf8b5a9262bf3ef7e101f8d1": 1000000000000,
  "0xec759db47a65f6537d630517f6cd3ca39c6f93d1": 1000000000000,
  "0xfaf78f23293cc537154c275c874ede0f8c8b8801": 1000000000000,
  "0xfbe506bdaf256682551873290d0a794d51bac4d1": 1000000000000
}
```

In this step, you must replace accounts.json with all of the above.

### 3. Join The Seele Test Network
After editing is complete, you need to use the flag -c and --accounts to start seele node in command.
`node start -c .\config\node1.json --accounts .\config\accounts.json`

For detailed usage, please see [Getting Started with Seele](Getting-Started-With-Seele.html).
