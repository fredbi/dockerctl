## dockerctl container ContainerUpdate

Change various configuration options of a container without having to recreate it.

```
dockerctl container ContainerUpdate [flags]
```

### Options

```
      --containerUpdateBody.BlkioWeight int                              Block IO weight (relative weight).
      --containerUpdateBody.CgroupParent cgroups                         Path to cgroups under which the container's `cgroup` is created. If the path is not absolute, the path is considered to be relative to the `cgroups` path of the init process. Cgroups are created if they do not already exist.
      --containerUpdateBody.CpuCount CPUCount                            The number of usable CPUs (Windows only).
                                                                         
                                                                         On Windows Server containers, the processor resource controls are mutually exclusive. The order of precedence is CPUCount first, then `CPUShares`, and `CPUPercent` last.
                                                                         
      --containerUpdateBody.CpuPercent CPUCount                          The usable percentage of the available CPUs (Windows only).
                                                                         
                                                                         On Windows Server containers, the processor resource controls are mutually exclusive. The order of precedence is CPUCount first, then `CPUShares`, and `CPUPercent` last.
                                                                         
      --containerUpdateBody.CpuPeriod int                                The length of a CPU period in microseconds.
      --containerUpdateBody.CpuQuota int                                 Microseconds of CPU time that the container can get in a CPU period.
      --containerUpdateBody.CpuRealtimePeriod int                        The length of a CPU real-time period in microseconds. Set to 0 to allocate no time allocated to real-time tasks.
      --containerUpdateBody.CpuRealtimeRuntime int                       The length of a CPU real-time runtime in microseconds. Set to 0 to allocate no time allocated to real-time tasks.
      --containerUpdateBody.CpuShares int                                An integer value representing this container's relative CPU weight versus other containers.
      --containerUpdateBody.CpusetCpus 0-3                               CPUs in which to allow execution (e.g., 0-3, `0,1`)
      --containerUpdateBody.CpusetMems string                            Memory nodes (MEMs) in which to allow execution (0-3, 0,1). Only effective on NUMA systems.
      --containerUpdateBody.IOMaximumBandwidth int                       Maximum IO in bytes per second for the container system drive (Windows only)
      --containerUpdateBody.IOMaximumIOps int                            Maximum IOps for the container system drive (Windows only)
      --containerUpdateBody.Init                                         Run an init inside the container that forwards signals and reaps processes. This field is omitted if empty, and the default (as configured on the daemon) is used.
      --containerUpdateBody.KernelMemory int                             Kernel memory limit in bytes.
      --containerUpdateBody.KernelMemoryTCP int                          Hard limit for kernel TCP buffer memory (in bytes).
      --containerUpdateBody.Memory int                                   Memory limit in bytes.
      --containerUpdateBody.MemoryReservation int                        Memory soft limit in bytes.
      --containerUpdateBody.MemorySwap -1                                Total memory limit (memory + swap). Set as -1 to enable unlimited swap.
      --containerUpdateBody.MemorySwappiness int                         Tune a container's memory swappiness behavior. Accepts an integer between 0 and 100.
      --containerUpdateBody.NanoCPUs int                                 CPU quota in units of 10<sup>-9</sup> CPUs.
      --containerUpdateBody.OomKillDisable                               Disable OOM Killer for the container.
      --containerUpdateBody.PidsLimit 0                                  Tune a container's PIDs limit. Set 0 or `-1` for unlimited, or `null` to not change.
                                                                         
      --containerUpdateBody.RestartPolicy.MaximumRetryCount on-failure   If on-failure is used, the number of times to retry before giving up
      --containerUpdateBody.RestartPolicy.Name always                    Enum: ["","always","unless-stopped","on-failure"]. - Empty string means not to restart
                                                                         - always Always restart
                                                                         - `unless-stopped` Restart always except when the user has manually stopped the container
                                                                         - `on-failure` Restart only when the container exit code is non-zero
                                                                         
  -h, --help                                                             help for ContainerUpdate
      --id string                                                        Required. ID or name of the container
      --update string                                                    Optional json string for [update]. 
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

* [dockerctl container](dockerctl_container.md)	 - 

###### Auto generated by spf13/cobra on 7-Nov-2025
