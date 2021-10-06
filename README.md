# dspcap

A humble bash script set that uses daemonset to capture tcpdump from all k8s nodes, then collect the captures.

## How to use

As simple as:

1. Call `dspcap-start context-name kubernetes-namespace` script to start capture.
2. Call `dspcap-stop context-name kubernetes-namespace` script to stop capture and collect result to `dspcap` directory.

## Finetune tcpdump command

Currently modify the `dspcap-start` script directly.
