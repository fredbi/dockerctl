## dockerctl service ServiceUpdate



```
dockerctl service ServiceUpdate [flags]
```

### Options

```
      --X-Registry-Auth string                                                                                                                                                        A base64-encoded auth configuration for pulling from private registries. [See the authentication section for details.](#section/Authentication)
      --body string                                                                                                                                                                   Optional json string for [body]. 
  -h, --help                                                                                                                                                                          help for ServiceUpdate
      --id string                                                                                                                                                                     Required. ID or name of service.
      --registryAuthFrom X-Registry-Auth                                                                                                                                              Enum: ["spec","previous-spec"]. If the X-Registry-Auth header is not specified, this parameter
                                                                                                                                                                                      indicates where to find registry authorization credentials.
                                                                                                                                                                                       (default "spec")
      --rollback previous                                                                                                                                                             Set to this parameter to previous to cause a server-side rollback
                                                                                                                                                                                      to the previous service spec. The supplied spec will be ignored in
                                                                                                                                                                                      this case.
                                                                                                                                                                                      
      --serviceUpdateBody.EndpointSpec.Mode string                                                                                                                                    Enum: ["vip","dnsrr"]. The mode of resolution to use for internal load balancing between tasks.
                                                                                                                                                                                       (default "vip")
      --serviceUpdateBody.Mode.Replicated.Replicas int                                                                                                                                
      --serviceUpdateBody.Name string                                                                                                                                                 Name of the service.
      --serviceUpdateBody.RollbackConfig.Delay int                                                                                                                                    Amount of time between rollback iterations, in nanoseconds.
      --serviceUpdateBody.RollbackConfig.FailureAction string                                                                                                                         Enum: ["continue","pause"]. Action to take if an rolled back task fails to run, or stops running during the rollback.
      --serviceUpdateBody.RollbackConfig.MaxFailureRatio float                                                                                                                        The fraction of tasks that may fail during a rollback before the failure action is invoked, specified as a floating point number between 0 and 1.
      --serviceUpdateBody.RollbackConfig.Monitor int                                                                                                                                  Amount of time to monitor each rolled back task for failures, in nanoseconds.
      --serviceUpdateBody.RollbackConfig.Order string                                                                                                                                 Enum: ["stop-first","start-first"]. The order of operations when rolling back a task. Either the old task is shut down before the new task is started, or the new task is started before the old task is shut down.
      --serviceUpdateBody.RollbackConfig.Parallelism int                                                                                                                              Maximum number of tasks to be rolled back in one iteration (0 means unlimited parallelism).
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Dir string                                                                                                                       The working directory for commands to run in.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.HealthCheck.Interval int                                                                                                         The time to wait between checks in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.HealthCheck.Retries int                                                                                                          The number of consecutive failures needed to consider a container as unhealthy. 0 means inherit.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.HealthCheck.StartPeriod int                                                                                                      Start period for the container to initialize before starting health-retries countdown in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.HealthCheck.Timeout int                                                                                                          The time to wait before considering the check to have hung. It should be 0 or at least 1000000 (1 ms). 0 means inherit.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Hostname string                                                                                                                  The hostname to use for the container, as a valid RFC 1123 hostname.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Image string                                                                                                                     The image name to use for the container
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Init                                                                                                                             Run an init inside the container that forwards signals and reaps processes. This field is omitted if empty, and the default (as configured on the daemon) is used.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Isolation string                                                                                                                 Enum: ["default","process","hyperv"]. Isolation technology of the containers running the service. (Windows only)
      --serviceUpdateBody.TaskTemplate.ContainerSpec.OpenStdin stdin                                                                                                                  Open stdin
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.CredentialSpec.Config CredentialSpec.File                                                                             Load credential spec from a Swarm Config with the given ID.
                                                                                                                                                                                      The specified config must also be present in the Configs field with the Runtime property set.
                                                                                                                                                                                      
                                                                                                                                                                                      <p><br /></p>
                                                                                                                                                                                      
                                                                                                                                                                                      
                                                                                                                                                                                      > **Note**: CredentialSpec.File, `CredentialSpec.Registry`, and `CredentialSpec.Config` are mutually exclusive.
                                                                                                                                                                                      
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.CredentialSpec.File CredentialSpecs                                                                                   Load credential spec from this file. The file is read by the daemon, and must be present in the
                                                                                                                                                                                      CredentialSpecs subdirectory in the docker data directory, which defaults to
                                                                                                                                                                                      `C:\ProgramData\Docker\` on Windows.
                                                                                                                                                                                      
                                                                                                                                                                                      For example, specifying `spec.json` loads `C:\ProgramData\Docker\CredentialSpecs\spec.json`.
                                                                                                                                                                                      
                                                                                                                                                                                      <p><br /></p>
                                                                                                                                                                                      
                                                                                                                                                                                      > **Note**: `CredentialSpec.File`, `CredentialSpec.Registry`, and `CredentialSpec.Config` are mutually exclusive.
                                                                                                                                                                                      
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.CredentialSpec.Registry HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Containers\CredentialSpecs   Load credential spec from this value in the Windows registry. The specified registry value must be
                                                                                                                                                                                      located in:
                                                                                                                                                                                      
                                                                                                                                                                                      HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Containers\CredentialSpecs
                                                                                                                                                                                      
                                                                                                                                                                                      <p><br /></p>
                                                                                                                                                                                      
                                                                                                                                                                                      
                                                                                                                                                                                      > **Note**: `CredentialSpec.File`, `CredentialSpec.Registry`, and `CredentialSpec.Config` are mutually exclusive.
                                                                                                                                                                                      
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Disable                                                                                                Disable SELinux
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Level string                                                                                           SELinux level label
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Role string                                                                                            SELinux role label
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.Type string                                                                                            SELinux type label
      --serviceUpdateBody.TaskTemplate.ContainerSpec.Privileges.SELinuxContext.User string                                                                                            SELinux user label
      --serviceUpdateBody.TaskTemplate.ContainerSpec.ReadOnly                                                                                                                         Mount the container's root filesystem as read only.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.StopGracePeriod int                                                                                                              Amount of time to wait for the container to terminate before forcefully killing it.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.StopSignal string                                                                                                                Signal to stop the container.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.TTY                                                                                                                              Whether a pseudo-TTY should be allocated.
      --serviceUpdateBody.TaskTemplate.ContainerSpec.User string                                                                                                                      The user inside the container.
      --serviceUpdateBody.TaskTemplate.ForceUpdate int                                                                                                                                A counter that triggers an update even if no relevant parameters have been changed.
      --serviceUpdateBody.TaskTemplate.LogDriver.Name string                                                                                                                          
      --serviceUpdateBody.TaskTemplate.NetworkAttachmentSpec.ContainerID string                                                                                                       ID of the container represented by this task
      --serviceUpdateBody.TaskTemplate.Placement.MaxReplicas int                                                                                                                      Maximum number of replicas for per node (default value is 0, which is unlimited)
      --serviceUpdateBody.TaskTemplate.PluginSpec.Disabled                                                                                                                            Disable the plugin once scheduled.
      --serviceUpdateBody.TaskTemplate.PluginSpec.Name string                                                                                                                         The name or 'alias' to use for the plugin.
      --serviceUpdateBody.TaskTemplate.PluginSpec.Remote string                                                                                                                       The plugin image reference to use.
      --serviceUpdateBody.TaskTemplate.Resources.Limits.MemoryBytes int                                                                                                               
      --serviceUpdateBody.TaskTemplate.Resources.Limits.NanoCPUs int                                                                                                                  
      --serviceUpdateBody.TaskTemplate.Resources.Reservation.MemoryBytes int                                                                                                          
      --serviceUpdateBody.TaskTemplate.Resources.Reservation.NanoCPUs int                                                                                                             
      --serviceUpdateBody.TaskTemplate.RestartPolicy.Condition string                                                                                                                 Enum: ["none","on-failure","any"]. Condition for restart.
      --serviceUpdateBody.TaskTemplate.RestartPolicy.Delay int                                                                                                                        Delay between restart attempts.
      --serviceUpdateBody.TaskTemplate.RestartPolicy.MaxAttempts int                                                                                                                  Maximum attempts to restart a given container before giving up (default value is 0, which is ignored).
      --serviceUpdateBody.TaskTemplate.RestartPolicy.Window int                                                                                                                       Windows is the time window used to evaluate the restart policy (default value is 0, which is unbounded).
      --serviceUpdateBody.TaskTemplate.Runtime string                                                                                                                                 Runtime is the type of runtime specified for the task executor.
      --serviceUpdateBody.UpdateConfig.Delay int                                                                                                                                      Amount of time between updates, in nanoseconds.
      --serviceUpdateBody.UpdateConfig.FailureAction string                                                                                                                           Enum: ["continue","pause","rollback"]. Action to take if an updated task fails to run, or stops running during the update.
      --serviceUpdateBody.UpdateConfig.MaxFailureRatio float                                                                                                                          The fraction of tasks that may fail during an update before the failure action is invoked, specified as a floating point number between 0 and 1.
      --serviceUpdateBody.UpdateConfig.Monitor int                                                                                                                                    Amount of time to monitor each updated task for failures, in nanoseconds.
      --serviceUpdateBody.UpdateConfig.Order string                                                                                                                                   Enum: ["stop-first","start-first"]. The order of operations when rolling out an updated task. Either the old task is shut down before the new task is started, or the new task is started before the old task is shut down.
      --serviceUpdateBody.UpdateConfig.Parallelism int                                                                                                                                Maximum number of tasks to be updated in one iteration (0 means unlimited parallelism).
      --version GET /services/{id}                                                                                                                                                    Required. The version number of the service object being updated. This is required to avoid conflicting writes. This version number should be the value as currently set on the service *before* the update. You can find the current version by calling GET /services/{id}
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
