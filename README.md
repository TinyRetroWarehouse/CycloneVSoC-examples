CycloneVSoC_Examples
====================
Examples using the FPSoC chip Cyclone V SoC

DE1-SoC
-------
Contains examples for the Terasic´s DE1-SoC board. Most of them are easily ported to other boards using CycloneV-SoC chips because they do not interact with the hardware in the board. The folder contains:

* Baremetal: Stand-alone projects without Operating System.
	* Build_Baremetal_SD: This brief tutorial explains how to build a SD card to run the baremetal examples provided in this repository.
    * Basic_Transfer_DMA_PL330: This is a complete example on moving data using the HPS Direct Memory Access Controller (DMAC) PL330. This example also shows how to switch on the cache memories L1 and L2 and how to configure the ACP port to access cache memories from L3.
    * This example uses a counter in the Performance Monitoring Unit (PMU) timer to measure seconds and build a second counter.

* FPGA_Hardware: Quartus projects describing the FPGA hardware needed in some of the examples.
	* FPGA_OCR_256K: this hardware project includes a 256kB On-Chip memory in the FPGA, implemented using 10Mb memory blocks. This memory is hanging at the beginning of the address space of the HPS-to-FPGA bridge.
    
* Linux_Applications:
    * Test_DMA_PL330_LKM: it shows how to use the DMA_PL330_LKM module.

* Linux_Modules: Linux Loadable Kernel Modules (LKM). All come with test apps in Linux_Applicatios folder. 
	* DMA_PL330_LKM_Basic: module to make data transfers using the PL330 DMAC available in HPS. It can move data between: FPGA memory, HPS On-chip RAM, uncached buffer in processor´s RAM and cached buffer in processor´s RAM (through APC).
	* DMA_PL330_LKM: module to make transfers between application and FPGA using PL330 DMAC. It uses char device driver interface to copy the data from application to a uncached or cached (through ACP) buffer in driver´s memory space. Later it uses PL330 DMAC to copy that buffer to FPGA.

* Useful_Scripts: Linux shell scripts to ease configuration (fixed IP, DHCP, etc.).
	* fixed_mac_dhcp.sh: fixes MAC and asks IP using DHCP protocol.
    