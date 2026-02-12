# Working with the Linux Scheduler

Understanding what a [scheduler](https://en.wikipedia.org/wiki/Scheduling_(computing)) is and how it works is fundamental to
learning how to run your [batch computing](https://en.wikipedia.org/wiki/Batch_processing) workloads on 
[high-performance computing (HPC)](https://en.wikipedia.org/wiki/High-performance_computing) systems. A scheduler manages all aspects of how your application will access and consume the compute, memory, storage, I/O, and network resources available to you
on these systems. There are a number of different distributed batch job schedulers — also sometimes referred to as workload or
resource managers — that you might encounter on an HPC system. For example, the 
[Slurm Workload Manager](https://en.wikipedia.org/wiki/Slurm_Workload_Manager) is the most popular one in use today. However, at
the core of every such system sits the Linux ([process](https://en.wikipedia.org/wiki/Process_(computing))) scheduler. 

In this first part of our series on Batch Computing, we introduce you to the concept of a scheduler — what they are, why they
exist, and how they work — using the Linux scheduler as our reference implementation and testbed. You will also learn how to
interact with the Linux scheduler on your personal computer by running a series of example exercises intended to teach you about
the most fundamental aspects of scheduling, including turning foreground processes into background ones and controlling their
priority relative to the other processes running on your system.

# Before you begin

To complete the exercises covered in this tutorial, you will need access to a computer with either:

- a Linux operating system (OS);
- a [Unix-like](https://en.wikipedia.org/wiki/Unix-like) OS such as [macOS](https://en.wikipedia.org/wiki/MacOS);
- a Linux-compatible OS environment such as the [Windows Subsystem for Linux (WSL)](https://en.wikipedia.org/wiki/VirtualBox); or
- a virtual machine running a Linux OS through a [hypervisor](https://en.wikipedia.org/wiki/Hypervisor) like [VirtualBox](https://www.virtualbox.org).

# Prerequisite knowledge required

# Additional Reference(s):
- 

# About COMPLECS

COMPrehensive Learning for end-users to Effectively utilize CyberinfraStructure (COMPLECS) is a CyberTraining program that
teaches non-programming concepts and skills needed to effectively use supercomputers. Topics include parallel computing, Linux
command-line tools, shell scripting, batch computing, data management, security, and how to get help.

# Acknowledgement

This material is based upon work supported by the [U.S. National Science Foundation](https://www.nsf.gov) under 
[Award No. CISE/OAC-2320934](https://www.nsf.gov/awardsearch/show-award/?AWD_ID=2320934). Any opinions, findings and conclusions
or recommendations expressed in this material are those of the author(s) and do not necessarily reflect the views of the U.S.
National Science Foundation.

<img src='https://nsf.widen.net/content/josuwjrmy6/png/NSF_Official_logo_Med_Res_600ppi.png' alt='NSF Logo' width='250'/>
