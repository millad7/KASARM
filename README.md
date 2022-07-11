# Breaking KASLR on Mobile Devices without Any Use of Cache Memory

This repository (Implementation.zip) demonstrats the implementations of our paper "Breaking KASLR on Mobile Devices without Any Use of Cache Memory". Our paper consists of two contributions. The first contribution is to break KASLR on ARM-based mobile devices and Intel CPUs. The second contribution is to find virtual address ranges on modern CPUs.

## Demos

This repository contains two demos. The first demo (Our_attack_on_Intel Folder) consists of the implementation of our attacks on Intel CPUs. The second demo (Our_attack_on_mobile folder) includes the implementation of our attacks on mobile devices using ARMv8-A CPUs. Our first demo should be tested on any Linux system, for example, Ubuntu 16.04. Also, we use Raspbian as our operating system for performing our second demo on the Raspberry Pi 3. 

## Build

we use "C4droid" and "C/C++ Program Compiler" IDEs for implementing our second demo on Android and iOS mobile devices, respectively. 

In order to compile our first demo, we can use GCC and Make (on Linux). Therefore, we use the following command in a terminal environment:

`make`

## Run

In order to run our first demo, the attacker should utilize the following command in a terminal environment:

`./ Our_attack_on_Intel`


Also, we run our second demo by C4droid and C/C++ Program Compiler IDEs.

## Demo 1

This demo is about breaking KASLR on Intel CPUs. This attack only works on CPUs supporting Intel TSX and does not require any privileges. 

It is worth noting that the attacker should derive timing thresholds between a valid, an invalid, and a non-canonical address. For this purpose, the attacker first runs the first demo and derives timing thresholds by observing the execution time of the accesses to valid, invalid, and non-canonical addresses. After that, the attacker can change the timing thresholds on the attack code and then run the second demo appropriately.

## Demo 2

This demo is about breaking KASLR on ARM-based CPUs. The major difference between the first and second demos is that the attacker uses a signal handler method as an exception handler on ARM devices, while he utilizes TSX on Intel CPUs as an exception handler. Another difference is that we use clock-gettime() for timing measurements of our attacks on ARM CPUs, whereas we use rdtsc for timing measurements of our attacks on Intel CPUs.

Also, the attacker should derive timing thresholds, according to the methods we explained in the first demo. Later on, the attacker can run the second demo on ARM mobile devices appropriately. Besides, this attack can only be performed on ARMv8-A and older families of ARM CPUs.





 
