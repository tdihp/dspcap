# dspcap

A humble bash script set that uses daemonset to capture tcpdump from all k8s nodes, then collect the captures.

## How to use

As simple as:

1. Call `dspcap-start` script to start capture.
2. Call `dspcap-stop` script to stop capture and collect result to `dspcap` directory.

## Customization

### Finetune tcpdump command

Modify `TCPDUMP_ARGS` line at the top of dspcap-start accordingly. Alternatively, locate and modify the `tcpdump` line.

### images

To change image used, modify `IMAGE` line at the top of dspcap-start accordingly. Most base images should work as long as nsenter (GNU or busybox version) is provided.

Below images are tested:

* `alpine:3.15` (default)
* `ubuntu:20.04`
* `mcr.microsoft.com/dotnet/runtime-deps:6.0`

### Capture selected nodes

An easy way to achieve this is to add a nodeSelector for the daemonset in dspcap-start, then add the same label for all nodes with `kubectl label node/<name>` 

e.g.

To add a section in `.spec.template.spec` of the daemonset:

```
      nodeSelector:
        foo: bar
```

Then label the target nodes, if not already applied:

```
kubectl label node/mynode1 foo=bar
kubectl label node/mynode2 foo=bar
```
