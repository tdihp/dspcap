# dspcap

A humble bash script set that uses daemonset to capture tcpdump from all k8s nodes, then collect the captures.

## How to use

As simple as:

1. Call `dspcap-start` script to start capture.
2. Call `dspcap-stop` script to stop capture and collect result to `dspcap` directory.

Installation:
```
wget https://raw.githubusercontent.com/tdihp/dspcap/master/dspcap-start
wget https://raw.githubusercontent.com/tdihp/dspcap/master/dspcap-stop
chmod +x dspcap-start dspcap-stop
./dspcap-start
./dspcap-stop
```
Then you will find all tcpdump files for your K8s nodes in dspcap directory. 

## Finetune tcpdump command

Currently modify the `dspcap-start` script directly.
