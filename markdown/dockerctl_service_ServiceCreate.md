## dockerctl service ServiceCreate



```
dockerctl service ServiceCreate [flags]
```

### Options

```
      --X-Registry-Auth string                                                                                                                                                        A base64-encoded auth configuration for pulling from private registries. [See the authentication section for details.](#section/Authentication)
      --body string                                                                                                                                                                   Optional json string for [body]. 
  -h, --help                                                                                                                                                                          help for ServiceCreate
      --serviceCreateBody.EndpointSpec.Mode string                                                                                                                                    Enum: ["vip","dnsrr"]. The mode of resolution to use for internal load balancing between tasks.
                                                                                                                                                                                       (default "vip")
      --serviceCreateBody.Mode.Replicated.Replicas int                                                                                                                                
      --serviceCreateBody.Name string                                                                                                                                                 Name of the service.
      --serviceCreateBody.RollbackConfig.Delay int                                                                                                                                    Amount of time between rollback iterations, in nanoseconds.
      --serviceCreateBody.RollbackConfig.FailureAction string                                                                                                                         Enum: ["continue","pause"]. Action to take if an rolled back task fails to run, or stops running during the rollback.
      --serviceCreateBody.RollbackConfig.MaxFailureRatio float                                                                                                                        The fraction of tasks that may fail during a rollback before the failure action is invoked, specified as a floating point number between 0 and 1.
      --serviceCreateBody.RollbackConfig.Monitor int                                                                                                                                  Amount of time to monitor each rolled back task for failures, in nanoseconds.
      --serviceCreateBody.RollbackConfig.Order string                                                                                                                                 Enum: ["stop-first","start-first"]. The order of operations when rolling back a task. Either the old task is shut down before the new task is started, or the new task is started before the old task is shut down.
      --serviceCreateBody.RollbackConfig.Parallelism int                                                                                                                              Maximum number of tasks to be rolled back in one iteration (0 means unlimited parallelism).
      --serviceCreateBody.TaskTemplate.ContainerSpec.Dir string                                                                                                                       The working directory for commands to run in.
      --serviceCreateBody.TaskTemplate.ContainerSpec.HealthCheck.Interval int                                                                                                         The time to wait between checks in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --serviceCreateBody.TaskTemplate.ContainerSpec.HealthCheck.Retries int                                                                                                          The number of consecutive failures needed to consider a container as unhealthy. 0 means inherit.
      --serviceCreateBody.TaskTemplate.ContainerSpec.HealthCheck.StartPeriod int                                                                                                      Start period for the container to initialize before starting health-retries countdown in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --serviceCreateBody.TaskTemplate.ContainerSpec.HealthCheck.Timeout int                                                                                                          The time to wait before considering the check to have hung. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --serviceCreateBody.TaskTemplate.ContainerSpec.Hostname string                                                                                                                  The hostname to use for the container, as a valid RFC 1123 hostname.
      --serviceCreateBody.TaskTemplate.ContainerSpec.Image string                                                                                                                     The image name to use for the container
      --serviceCreateBody.TaskTemplate.ContainerSpec.Init                                                                                                                             Run an init inside the container that forwards signals and reaps processes. This field is omitted if empty, and the default (as configured on the daemon) is used.
      --serviceCreateBody.TaskTemplate.ContainerSpec.Isolation string                                                                                                                 Enum: ["default","process","hyperv"]. Isolation technology of the containers running the service. (Windows only)
      --serviceCreateBody.TaskTemplate.ContainerSpec.OpenStdin stdin                                                                                                                  Open stdin
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.CredentialSpec.Config CredentialSpec.File                                                                             Load credential spec from a Swarm Config with the given ID.
                                                                                                                                                                                      The specified config must also be present in the Configs field with the Runtime property set.
                                                                                                                                                                                      
                                                                                                                                                                                      <p><br /></p>
                                                                                                                                                                                      
                                                                                                                                                                                      
                                                                                                                                                                                      > **Note**: CredentialSpec.File, `CredentialSpec.Registry`, and `CredentialSpec.Config` are mutually exclusive.
                                                                                                                                                                                      
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.CredentialSpec.File CredentialSpecs                                                                                   Load credential spec from this file. The file is read by the daemon, and must be present in the
                                                                                                                                                                                      CredentialSpecs subdirectory in the docker data directory, which defaults to
                                                                                                                                                                                      `C:\ProgramData\Docker\` on Windows.
                                                                                                                                                                                      
                                                                                                                                                                                      For example, specifying `spec.json` loads `C:\ProgramData\Docker\CredentialSpecs\spec.json`.
                                                                                                                                                                                      
                                                                                                                                                                                      <p><br /></p>
                                                                                                                                                                                      
                                                                                                                                                                                      > **Note**: `CredentialSpec.File`, `CredentialSpec.Registry`, and `CredentialSpec.Config` are mutually exclusive.
                                                                                                                                                                                      
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.CredentialSpec.Registry HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Containers\CredentialSpecs   Load credential spec from this value in the Windows registry. The specified registry value must be
                                                                                                                                                                                      located in:
                                                                                                                                                                                      
                                                                                                                                                                                      HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Containers\CredentialSpecs
                                                                                                                                                                                      
                                                                                                                                                                                      <p><br /></p>
                                                                                                                                                                                      
                                                                                                                                                                                      
                                                                                                                                                                                      > **Note**: `CredentialSpec.File`, `CredentialSpec.Registry`, and `CredentialSpec.Config` are mutually exclusive.
                                                                                                                                                                                      
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Disable                                                                                                Disable SELinux
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Level string                                                                                           SELinux level label
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Role string                                                                                            SELinux role label
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Type string                                                                                            SELinux type label
      --serviceCreateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.User string                                                                                            SELinux user label
      --serviceCreateBody.TaskTemplate.ContainerSpec.ReadOnly                                                                                                                         Mount the container's root filesystem as read only.
      --serviceCreateBody.TaskTemplate.ContainerSpec.StopGracePeriod int                                                                                                              Amount of time to wait for the container to terminate before forcefully killing it.
      --serviceCreateBody.TaskTemplate.ContainerSpec.StopSignal string                                                                                                                Signal to stop the container.
      --serviceCreateBody.TaskTemplate.ContainerSpec.TTY                                                                                                                              Whether a pseudo-TTY should be allocated.
      --serviceCreateBody.TaskTemplate.ContainerSpec.User string                                                                                                                      The user inside the container.
      --serviceCreateBody.TaskTemplate.ForceUpdate int                                                                                                                                A counter that triggers an update even if no relevant parameters have been changed.
      --serviceCreateBody.TaskTemplate.LogDriver.Name string                                                                                                                          
      --serviceCreateBody.TaskTemplate.NetworkAttachmentSpec.ContainerID string                                                                                                       ID of the container represented by this task
      --serviceCreateBody.TaskTemplate.Placement.MaxReplicas int                                                                                                                      Maximum number of replicas for per node (default value is 0, which is unlimited)
      --serviceCreateBody.TaskTemplate.PluginSpec.Disabled                                                                                                                            Disable the plugin once scheduled.
      --serviceCreateBody.TaskTemplate.PluginSpec.Name string                                                                                                                         The name or 'alias' to use for the plugin.
      --serviceCreateBody.TaskTemplate.PluginSpec.Remote string                                                                                                                       The plugin image reference to use.
      --serviceCreateBody.TaskTemplate.Resources.Limits.MemoryBytes int                                                                                                               
      --serviceCreateBody.TaskTemplate.Resources.Limits.NanoCPUs int                                                                                                                  
      --serviceCreateBody.TaskTemplate.Resources.Reservation.MemoryBytes int                                                                                                          
      --serviceCreateBody.TaskTemplate.Resources.Reservation.NanoCPUs int                                                                                                             
      --serviceCreateBody.TaskTemplate.RestartPolicy.Condition string                                                                                                                 Enum: ["none","on-failure","any"]. Condition for restart.
      --serviceCreateBody.TaskTemplate.RestartPolicy.Delay int                                                                                                                        Delay between restart attempts.
      --serviceCreateBody.TaskTemplate.RestartPolicy.MaxAttempts int                                                                                                                  Maximum attempts to restart a given container before giving up (default value is 0, which is ignored).
      --serviceCreateBody.TaskTemplate.RestartPolicy.Window int                                                                                                                       Windows is the time window used to evaluate the restart policy (default value is 0, which is unbounded).
      --serviceCreateBody.TaskTemplate.Runtime string                                                                                                                                 Runtime is the type of runtime specified for the task executor.
      --serviceCreateBody.UpdateConfig.Delay int                                                                                                                                      Amount of time between updates, in nanoseconds.
      --serviceCreateBody.UpdateConfig.FailureAction string                                                                                                                           Enum: ["continue","pause","rollback"]. Action to take if an updated task fails to run, or stops running during the update.
      --serviceCreateBody.UpdateConfig.MaxFailureRatio float                                                                                                                          The fraction of tasks that may fail during an update before the failure action is invoked, specified as a floating point number between 0 and 1.
      --serviceCreateBody.UpdateConfig.Monitor int                                                                                                                                    Amount of time to monitor each updated task for failures, in nanoseconds.
      --serviceCreateBody.UpdateConfig.Order string                                                                                                                                   Enum: ["stop-first","start-first"]. The order of operations when rolling out an updated task. Either the old task is shut down before the new task is started, or the new task is started before the old task is shut down.
      --serviceCreateBody.UpdateConfig.Parallelism int                                                                                                                                Maximum number of tasks to be updated in one iteration (0 means unlimited parallelism).
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

* [dockerctl service](dockerctl_service.md)	 - 

###### Auto generated by spf13/cobra on 7-Nov-2025
