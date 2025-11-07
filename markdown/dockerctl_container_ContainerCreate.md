## dockerctl container ContainerCreate



```
dockerctl container ContainerCreate [flags]
```

### Options

```
      --body string                                                                             Optional json string for [body]. Container to create
      --containerCreateBody.ArgsEscaped                                                         Command is already escaped (Windows only)
      --containerCreateBody.AttachStderr stderr                                                 Whether to attach to stderr. (default true)
      --containerCreateBody.AttachStdin stdin                                                   Whether to attach to stdin.
      --containerCreateBody.AttachStdout stdout                                                 Whether to attach to stdout. (default true)
      --containerCreateBody.Domainname string                                                   The domain name to use for the container.
      --containerCreateBody.Healthcheck.Interval int                                            The time to wait between checks in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --containerCreateBody.Healthcheck.Retries int                                             The number of consecutive failures needed to consider a container as unhealthy. 0 means inherit.
      --containerCreateBody.Healthcheck.StartPeriod int                                         Start period for the container to initialize before starting health-retries countdown in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --containerCreateBody.Healthcheck.Timeout int                                             The time to wait before considering the check to have hung. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --containerCreateBody.HostConfig.AutoRemove RestartPolicy                                 Automatically remove the container when the container's process exits. This has no effect if RestartPolicy is set.
      --containerCreateBody.HostConfig.BlkioWeight int                                          Block IO weight (relative weight).
      --containerCreateBody.HostConfig.Cgroup string                                            Cgroup to use for the container.
      --containerCreateBody.HostConfig.CgroupParent cgroups                                     Path to cgroups under which the container's `cgroup` is created. If the path is not absolute, the path is considered to be relative to the `cgroups` path of the init process. Cgroups are created if they do not already exist.
      --containerCreateBody.HostConfig.CgroupnsMode "private"                                   Enum: ["private","host"]. cgroup namespace mode for the container. Possible values are:
                                                                                                
                                                                                                - "private": the container runs in its own private cgroup namespace
                                                                                                - `"host"`: use the host system's cgroup namespace
                                                                                                
                                                                                                If not specified, the daemon default is used, which can either be `"private"`
                                                                                                or `"host"`, depending on daemon version, kernel support and configuration.
                                                                                                
      --containerCreateBody.HostConfig.ContainerIDFile string                                   Path to a file where the container ID is written
      --containerCreateBody.HostConfig.CpuCount CPUCount                                        The number of usable CPUs (Windows only).
                                                                                                
                                                                                                On Windows Server containers, the processor resource controls are mutually exclusive. The order of precedence is CPUCount first, then `CPUShares`, and `CPUPercent` last.
                                                                                                
      --containerCreateBody.HostConfig.CpuPercent CPUCount                                      The usable percentage of the available CPUs (Windows only).
                                                                                                
                                                                                                On Windows Server containers, the processor resource controls are mutually exclusive. The order of precedence is CPUCount first, then `CPUShares`, and `CPUPercent` last.
                                                                                                
      --containerCreateBody.HostConfig.CpuPeriod int                                            The length of a CPU period in microseconds.
      --containerCreateBody.HostConfig.CpuQuota int                                             Microseconds of CPU time that the container can get in a CPU period.
      --containerCreateBody.HostConfig.CpuRealtimePeriod int                                    The length of a CPU real-time period in microseconds. Set to 0 to allocate no time allocated to real-time tasks.
      --containerCreateBody.HostConfig.CpuRealtimeRuntime int                                   The length of a CPU real-time runtime in microseconds. Set to 0 to allocate no time allocated to real-time tasks.
      --containerCreateBody.HostConfig.CpuShares int                                            An integer value representing this container's relative CPU weight versus other containers.
      --containerCreateBody.HostConfig.CpusetCpus 0-3                                           CPUs in which to allow execution (e.g., 0-3, `0,1`)
      --containerCreateBody.HostConfig.CpusetMems string                                        Memory nodes (MEMs) in which to allow execution (0-3, 0,1). Only effective on NUMA systems.
      --containerCreateBody.HostConfig.IOMaximumBandwidth int                                   Maximum IO in bytes per second for the container system drive (Windows only)
      --containerCreateBody.HostConfig.IOMaximumIOps int                                        Maximum IOps for the container system drive (Windows only)
      --containerCreateBody.HostConfig.Init                                                     Run an init inside the container that forwards signals and reaps processes. This field is omitted if empty, and the default (as configured on the daemon) is used.
      --containerCreateBody.HostConfig.IpcMode "none"                                           IPC sharing mode for the container. Possible values are:
                                                                                                
                                                                                                - "none": own private IPC namespace, with /dev/shm not mounted
                                                                                                - `"private"`: own private IPC namespace
                                                                                                - `"shareable"`: own private IPC namespace, with a possibility to share it with other containers
                                                                                                - `"container:<name|id>"`: join another (shareable) container's IPC namespace
                                                                                                - `"host"`: use the host system's IPC namespace
                                                                                                
                                                                                                If not specified, daemon default is used, which can either be `"private"`
                                                                                                or `"shareable"`, depending on daemon version and configuration.
                                                                                                
      --containerCreateBody.HostConfig.Isolation string                                         Enum: ["default","process","hyperv"]. Isolation technology of the container. (Windows only)
      --containerCreateBody.HostConfig.KernelMemory int                                         Kernel memory limit in bytes.
      --containerCreateBody.HostConfig.KernelMemoryTCP int                                      Hard limit for kernel TCP buffer memory (in bytes).
      --containerCreateBody.HostConfig.LogConfig.Type string                                    Enum: ["json-file","syslog","journald","gelf","fluentd","awslogs","splunk","etwlogs","none"]. 
      --containerCreateBody.HostConfig.Memory int                                               Memory limit in bytes.
      --containerCreateBody.HostConfig.MemoryReservation int                                    Memory soft limit in bytes.
      --containerCreateBody.HostConfig.MemorySwap -1                                            Total memory limit (memory + swap). Set as -1 to enable unlimited swap.
      --containerCreateBody.HostConfig.MemorySwappiness int                                     Tune a container's memory swappiness behavior. Accepts an integer between 0 and 100.
      --containerCreateBody.HostConfig.NanoCPUs int                                             CPU quota in units of 10<sup>-9</sup> CPUs.
      --containerCreateBody.HostConfig.NetworkMode bridge                                       Network mode to use for this container. Supported standard values are: bridge, `host`, `none`, and `container:<name|id>`. Any other value is taken as a custom network's name to which this container should connect to.
      --containerCreateBody.HostConfig.OomKillDisable                                           Disable OOM Killer for the container.
      --containerCreateBody.HostConfig.OomScoreAdj int                                          An integer value containing the score given to the container in order to tune OOM killer preferences.
      --containerCreateBody.HostConfig.PidMode "container:<name|id>"                            Set the PID (Process) Namespace mode for the container. It can be either:
                                                                                                
                                                                                                - "container:<name|id>": joins another container's PID namespace
                                                                                                - `"host"`: use the host's PID namespace inside the container
                                                                                                
      --containerCreateBody.HostConfig.PidsLimit 0                                              Tune a container's PIDs limit. Set 0 or `-1` for unlimited, or `null` to not change.
                                                                                                
      --containerCreateBody.HostConfig.Privileged                                               Gives the container full access to the host.
      --containerCreateBody.HostConfig.PublishAllPorts /proc/sys/net/ipv4/ip_local_port_range   Allocates an ephemeral host port for all of a container's
                                                                                                exposed ports.
                                                                                                
                                                                                                Ports are de-allocated when the container stops and allocated when the container starts.
                                                                                                The allocated port might be changed when restarting the container.
                                                                                                
                                                                                                The port is selected from the ephemeral port range that depends on the kernel.
                                                                                                For example, on Linux the range is defined by /proc/sys/net/ipv4/ip_local_port_range.
                                                                                                
      --containerCreateBody.HostConfig.ReadonlyRootfs                                           Mount the container's root filesystem as read only.
      --containerCreateBody.HostConfig.RestartPolicy.MaximumRetryCount on-failure               If on-failure is used, the number of times to retry before giving up
      --containerCreateBody.HostConfig.RestartPolicy.Name always                                Enum: ["","always","unless-stopped","on-failure"]. - Empty string means not to restart
                                                                                                - always Always restart
                                                                                                - `unless-stopped` Restart always except when the user has manually stopped the container
                                                                                                - `on-failure` Restart only when the container exit code is non-zero
                                                                                                
      --containerCreateBody.HostConfig.Runtime string                                           Runtime to use with this container.
      --containerCreateBody.HostConfig.ShmSize /dev/shm                                         Size of /dev/shm in bytes. If omitted, the system uses 64MB.
      --containerCreateBody.HostConfig.UTSMode string                                           UTS namespace to use for the container.
      --containerCreateBody.HostConfig.UsernsMode string                                        Sets the usernamespace mode for the container when usernamespace remapping option is enabled.
      --containerCreateBody.HostConfig.VolumeDriver string                                      Driver that this container uses to mount volumes.
      --containerCreateBody.Hostname string                                                     The hostname to use for the container, as a valid RFC 1123 hostname.
      --containerCreateBody.Image string                                                        The name of the image to use when creating the container
      --containerCreateBody.MacAddress string                                                   MAC address of the container.
      --containerCreateBody.NetworkDisabled                                                     Disable networking for the container.
      --containerCreateBody.OpenStdin stdin                                                     Open stdin
      --containerCreateBody.StdinOnce stdin                                                     Close stdin after one attached client disconnects
      --containerCreateBody.StopSignal string                                                   Signal to stop a container as a string or unsigned integer. (default "SIGTERM")
      --containerCreateBody.StopTimeout int                                                     Timeout to stop a container in seconds. (default 10)
      --containerCreateBody.Tty stdin                                                           Attach standard streams to a TTY, including stdin if it is not closed.
      --containerCreateBody.User string                                                         The user that commands are run as inside the container.
      --containerCreateBody.WorkingDir string                                                   The working directory for commands to run in.
  -h, --help                                                                                    help for ContainerCreate
      --name /?[a-zA-Z0-9][a-zA-Z0-9_.-]+                                                       Assign the specified name to the container. Must match /?[a-zA-Z0-9][a-zA-Z0-9_.-]+.
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
