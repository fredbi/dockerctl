## dockerctl swarm SwarmInit



```
dockerctl swarm SwarmInit [flags]
```

### Options

```
      --body string                                                      Optional json string for [body]. 
  -h, --help                                                             help for SwarmInit
      --swarmInitBody.AdvertiseAddr 192.168.1.1:4567                     Externally reachable address advertised to other nodes. This can either be an address/port combination in the form 192.168.1.1:4567, or an interface followed by a port number, like `eth0:4567`. If the port number is omitted, the port number from the listen address is used. If `AdvertiseAddr` is not specified, it will be automatically detected when possible.
      --swarmInitBody.DataPathAddr <ip|interface>                        Address or interface to use for data path traffic (format: <ip|interface>), for example,  `192.168.1.1`,
                                                                         or an interface, like `eth0`. If `DataPathAddr` is unspecified, the same address as `AdvertiseAddr`
                                                                         is used.
                                                                         
                                                                         The `DataPathAddr` specifies the address that global scope network drivers will publish towards other
                                                                         nodes in order to reach the containers running on this node. Using this parameter it is possible to
                                                                         separate the container data traffic from the management traffic of the cluster.
                                                                         
      --swarmInitBody.ForceNewCluster                                    Force creation of a new swarm.
      --swarmInitBody.ListenAddr 192.168.1.1:4567                        Listen address used for inter-manager communication, as well as determining the networking interface used for the VXLAN Tunnel Endpoint (VTEP). This can either be an address/port combination in the form 192.168.1.1:4567, or an interface followed by a port number, like `eth0:4567`. If the port number is omitted, the default swarm listening port is used.
      --swarmInitBody.Spec.CAConfig.NodeCertExpiry int                   The duration node certificates are issued for.
      --swarmInitBody.Spec.CAConfig.SigningCACert string                 The desired signing CA certificate for all swarm node TLS leaf certificates, in PEM format.
      --swarmInitBody.Spec.CAConfig.SigningCAKey string                  The desired signing CA key for all swarm node TLS leaf certificates, in PEM format.
      --swarmInitBody.Spec.Dispatcher.HeartbeatPeriod int                The delay for an agent to send a heartbeat to the dispatcher.
      --swarmInitBody.Spec.EncryptionConfig.AutoLockManagers             If set, generate a key and use it to lock data stored on the managers.
      --swarmInitBody.Spec.Name string                                   Name of the swarm.
      --swarmInitBody.Spec.Orchestration.TaskHistoryRetentionLimit int   The number of historic tasks to keep per instance or node. If negative, never remove completed or failed tasks.
      --swarmInitBody.Spec.Raft.ElectionTick ElectionTick                The number of ticks that a follower will wait for a message from the leader before becoming a candidate and starting an election. ElectionTick must be greater than `HeartbeatTick`.
                                                                         
                                                                         A tick currently defaults to one second, so these translate directly to seconds currently, but this is NOT guaranteed.
                                                                         
      --swarmInitBody.Spec.Raft.HeartbeatTick int                        The number of ticks between heartbeats. Every HeartbeatTick ticks, the leader will send a heartbeat to the followers.
                                                                         
                                                                         A tick currently defaults to one second, so these translate directly to seconds currently, but this is NOT guaranteed.
                                                                         
      --swarmInitBody.Spec.TaskDefaults.LogDriver.Name string            The log driver to use as a default for new tasks.
                                                                         
```

### Options inherited from parent commands

```
      --base-path string   For example: /v1.41 (default "/v1.41")
      --config string      config file path
      --debug              output debug logs
      --dry-run            do not send the request to server
      --hostname string    hostname of the service (default "localhost")
      --scheme string      Choose from: [http https] (default "http")
```

### SEE ALSO

* [dockerctl swarm](dockerctl_swarm.md)	 - 

###### Auto generated by spf13/cobra on 7-Nov-2025
