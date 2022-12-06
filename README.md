# CMPE283-Assignment-2
- Our task is to change the CPUID emulation code in KVM such that it returns more information when a particular CPUID "leaf function" is invoked.
-For CPUID leaf node %eax=0x4FFFFFFC:
- We have to return total number of exits (all catagories) in %eax

- For CPUID leaf node %eax=0x4FFFFFFD:
We have to return the top 32 bits of the total time spent processing all exits in%ebx.
The low 32 bits of the total time spent processing all exits in%ecx will be returned. * Return values for %ebx and %ecx are measured in processor cycles across all VCPUs. At a high level, you will need to:
- Modify the kernel code with the assignment's functionality:
Decide where to put the measurement code.
Create new CPUID leaf 0x4FFFFFFD, 0x4FFFFFFC
- Make a user-mode application that executes the necessary CPUID instructions needed to test.
This is possible on Ubuntu by installing the 'cpuid' package.
Run this user mode program in the nested VM
- Check for correct output.
