# wireguard per-peer fwmark support

### usage

```
# wg set ... fwmark 0xaa55
# wg set ... peer ... xor-fwmark 0x55aa
```

the fwmark of specified peer will be: 0xaa55 ^ 0x55aa = 0xffff

### example output

```
# wg show ...

interface: ...
  public key: ...
  private key: (hidden)
  listening port: ...
  fwmark: 0xaa55

peer: ...
  endpoint: ...
  allowed ips: ...
  latest handshake: ...
  transfer: ... received, ... sent
  persistent keepalive: every ... seconds
  xor fwmark: 0x55aa
```
 
```
# wg showconf ...

[Interface]
ListenPort = ...
FwMark = 0xaa55
PrivateKey = ...

[Peer]
PublicKey = ...
AllowedIPs = ...
Endpoint = ...
PersistentKeepalive = ...
XorFwMark = 0x55aa
```

command ``wg setconf`` is also supported