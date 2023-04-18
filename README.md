# x4n6.github.io

This page will be used to describe techniches and tools on how to conduct forensic analysis.


# Investigation Checklist

## Memory Analysis

Acquisition/Preservation

1. Acquire using the tool of choice (Dumpit, EnCase, Magnet Acquire)
2. Memory from VMEM
* Don't forget to copy the snapshots (VMSN and VSSD)
* Convert using vss2core (with -W8 switch)
* Convert the memory.dmp to RAW using imagecopy (volatility)

Keyword Search
1. Run bulk_extractor with -F ioc.txt -E find
2. RAW search with EnCase for wordlist (IOCs)
3. Run strings (GNU Linux is best and faster) on memory dump

Scan and AntiVirus
1. Run volatility yarascan with YaraRules (-y switch)
2. Dump all the DLLs and run with antivirus solution
3. Dump all the processes and run antivirus solution

Other Techniques
1. Mount the memory with MemprocFS for faster analysis
2. Check unique environment variables (envars)
3. Run volatility netscan and check for suspicious connections
* TCP/445 (outbound): Lateral movement
* TCP/22 (out): lateral movement 

Disk Analysis
1. RAW search with EnCase for wordlist (IOCs)
2. Mount the disk as file system and scan with antivirus solution  
