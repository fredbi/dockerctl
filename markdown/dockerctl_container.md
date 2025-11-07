## dockerctl container



### Options

```
  -h, --help   help for container
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

* [dockerctl](dockerctl.md)	 - 
* [dockerctl container ContainerArchive](dockerctl_container_ContainerArchive.md)	 - Get a tar archive of a resource in the filesystem of container id.
* [dockerctl container ContainerArchiveInfo](dockerctl_container_ContainerArchiveInfo.md)	 - A response header `X-Docker-Container-Path-Stat` is return containing a base64 - encoded JSON object with some filesystem header information about the path.
* [dockerctl container ContainerAttach](dockerctl_container_ContainerAttach.md)	 - Attach to a container to read its output or send it input. You can attach to the same container multiple times and you can reattach to containers that have been detached.

Either the `stream` or `logs` parameter must be `true` for this endpoint to do anything.

See [the documentation for the `docker attach` command](https://docs.docker.com/engine/reference/commandline/attach/) for more details.

### Hijacking

This endpoint hijacks the HTTP connection to transport `stdin`, `stdout`, and `stderr` on the same socket.

This is the response from the daemon for an attach request:

```
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

[STREAM]
```

After the headers and two new lines, the TCP connection can now be used for raw, bidirectional communication between the client and server.

To hint potential proxies about connection hijacking, the Docker client can also optionally send connection upgrade headers.

For example, the client sends this request to upgrade the connection:

```
POST /containers/16253994b7c4/attach?stream=1&stdout=1 HTTP/1.1
Upgrade: tcp
Connection: Upgrade
```

The Docker daemon will respond with a `101 UPGRADED` response, and will similarly follow with the raw stream:

```
HTTP/1.1 101 UPGRADED
Content-Type: application/vnd.docker.raw-stream
Connection: Upgrade
Upgrade: tcp

[STREAM]
```

### Stream format

When the TTY setting is disabled in [`POST /containers/create`](#operation/ContainerCreate), the stream over the hijacked connected is multiplexed to separate out `stdout` and `stderr`. The stream consists of a series of frames, each containing a header and a payload.

The header contains the information which the stream writes (`stdout` or `stderr`). It also contains the size of the associated frame encoded in the last four bytes (`uint32`).

It is encoded on the first eight bytes like this:

```go
header := [8]byte{STREAM_TYPE, 0, 0, 0, SIZE1, SIZE2, SIZE3, SIZE4}
```

`STREAM_TYPE` can be:

- 0: `stdin` (is written on `stdout`)
- 1: `stdout`
- 2: `stderr`

`SIZE1, SIZE2, SIZE3, SIZE4` are the four bytes of the `uint32` size encoded as big endian.

Following the header is the payload, which is the specified number of bytes of `STREAM_TYPE`.

The simplest way to implement this protocol is the following:

1. Read 8 bytes.
2. Choose `stdout` or `stderr` depending on the first byte.
3. Extract the frame size from the last four bytes.
4. Read the extracted size and output it on the correct output.
5. Goto 1.

### Stream format when using a TTY

When the TTY setting is enabled in [`POST /containers/create`](#operation/ContainerCreate), the stream is not multiplexed. The data exchanged over the hijacked connection is simply the raw data from the process PTY and client's `stdin`.

* [dockerctl container ContainerAttachWebsocket](dockerctl_container_ContainerAttachWebsocket.md)	 - 
* [dockerctl container ContainerChanges](dockerctl_container_ContainerChanges.md)	 - Returns which files in a container's filesystem have been added, deleted,
or modified. The `Kind` of modification can be one of:

- `0`: Modified
- `1`: Added
- `2`: Deleted

* [dockerctl container ContainerCreate](dockerctl_container_ContainerCreate.md)	 - 
* [dockerctl container ContainerDelete](dockerctl_container_ContainerDelete.md)	 - 
* [dockerctl container ContainerExport](dockerctl_container_ContainerExport.md)	 - Export the contents of a container as a tarball.
* [dockerctl container ContainerInspect](dockerctl_container_ContainerInspect.md)	 - Return low-level information about a container.
* [dockerctl container ContainerKill](dockerctl_container_ContainerKill.md)	 - Send a POSIX signal to a container, defaulting to killing to the container.
* [dockerctl container ContainerList](dockerctl_container_ContainerList.md)	 - Returns a list of containers. For details on the format, see [the inspect endpoint](#operation/ContainerInspect).

Note that it uses a different, smaller representation of a container than inspecting a single container. For example,
the list of linked containers is not propagated .

* [dockerctl container ContainerLogs](dockerctl_container_ContainerLogs.md)	 - Get `stdout` and `stderr` logs from a container.

Note: This endpoint works only for containers with the `json-file` or `journald` logging driver.

* [dockerctl container ContainerPause](dockerctl_container_ContainerPause.md)	 - Use the freezer cgroup to suspend all processes in a container.

Traditionally, when suspending a process the `SIGSTOP` signal is used, which is observable by the process being suspended. With the freezer cgroup the process is unaware, and unable to capture, that it is being suspended, and subsequently resumed.

* [dockerctl container ContainerPrune](dockerctl_container_ContainerPrune.md)	 - 
* [dockerctl container ContainerRename](dockerctl_container_ContainerRename.md)	 - 
* [dockerctl container ContainerResize](dockerctl_container_ContainerResize.md)	 - Resize the TTY for a container.
* [dockerctl container ContainerRestart](dockerctl_container_ContainerRestart.md)	 - 
* [dockerctl container ContainerStart](dockerctl_container_ContainerStart.md)	 - 
* [dockerctl container ContainerStats](dockerctl_container_ContainerStats.md)	 - This endpoint returns a live stream of a container’s resource usage
statistics.

The `precpu_stats` is the CPU statistic of the *previous* read, and is
used to calculate the CPU usage percentage. It is not an exact copy
of the `cpu_stats` field.

If either `precpu_stats.online_cpus` or `cpu_stats.online_cpus` is
nil then for compatibility with older daemons the length of the
corresponding `cpu_usage.percpu_usage` array should be used.

* [dockerctl container ContainerStop](dockerctl_container_ContainerStop.md)	 - 
* [dockerctl container ContainerTop](dockerctl_container_ContainerTop.md)	 - On Unix systems, this is done by running the `ps` command. This endpoint is not supported on Windows.
* [dockerctl container ContainerUnpause](dockerctl_container_ContainerUnpause.md)	 - Resume a container which has been paused.
* [dockerctl container ContainerUpdate](dockerctl_container_ContainerUpdate.md)	 - Change various configuration options of a container without having to recreate it.
* [dockerctl container ContainerWait](dockerctl_container_ContainerWait.md)	 - Block until a container stops, then returns the exit code.
* [dockerctl container PutContainerArchive](dockerctl_container_PutContainerArchive.md)	 - Upload a tar archive to be extracted to a path in the filesystem of container id.

###### Auto generated by spf13/cobra on 7-Nov-2025
