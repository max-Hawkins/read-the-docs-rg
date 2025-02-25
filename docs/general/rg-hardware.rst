=======================
Rogues Gallery Hardware
=======================

The Rogues Gallery testbed is composed of both "virtual" resources and
"physical" servers and test platforms. The figure below shows the Rogues
Gallery resources at a high level with suggested paths from development
VMs to the actual hardware. Discussion of the filesystems you have
access to can be found `here <RG-Filesystems>`__.

For instance, if you're able to test your compilation and do debugging
on the rg-fpga-dev VMs, you can then use the same code on the physical
"flubber" boxes to test your code with a PCI Express-based FPGA. We
currently have three pairs of development VMs that map to physical
hardware, as described more in the tables below.

.. figure:: ../figures/general/rg-machine-overview.png
   :alt: Rogues Gallery Hardware

RG Virtual Machines
===================

Note that VMs are meant as development resources since we may need to
reboot physical hardware often to apply new drivers or reconfigure for
specific experiments. These VMs have limited CPU cores and memory, but
we can reconfigure them as needed or provide additional resources for
long-running simulations. Local storage refers to space hosted within
the VM for /localscratch. Except where noted, all machines are running
RHEL8 or Ubuntu 20.04.

RG Virtual Machines
--------------------
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - CPU
      - Memory (GB)
      - Local Storage (GB)
      - Software and Features
    * - rg-emu-dev
      - 4 core, E312xx
      - 4
      - 33
      - Emu simulator and tools
    * - rg-fpga-dev<1-3>
      - 4 core, E312xx
      - 16
      - 250
      - RHEL 8 VM for FPGA tools
    * - rg-fpga-dev4
      - 4 core, E312xx
      - 16
      - 250
      - Ubuntu 20.04 VM for FPGA tools
    * - rg-neuro-dev
      - 4 core, Broadwell
      - 8
      - 450
      - ROS, FPAA tools
    * - rg-quantum-dev
      - 4 core, Broadwell
      - 8
      - 130
      - XACC, Qiskit
      


RG Physical Machines
====================

Arm HPC
--------------------
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - CPU
      - Memory (GB)
      - Network
      - Cards
      - Notes
    * - octavius<1-16>
      - A64FX
      - 32 GB HBM2e
      - EDR IB
      - 
      - 

Near-Memory
--------------------

The Pathfinder system consists of 4 chassis while the Emu Chick is a one chassis system. We recommend that you use the newer Pathfinder system for your work.

.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - Nodes
      - Memory (GB)
      - LCEs
      - Network
      - Notes
    * - pathfinder (4 chassis)
      - 32  
      - 2048
      - 784
      - RapidIO 2.0, 10 GE
      - 
    * - karrawingi (Emu Chick, 1 chassis)
      - 8
      - 512
      - 64
      - RapidIO, 1 GE
      - karrawingi-login

Neuromorphic/AI
--------------------
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - CPU
      - Memory (GB)
      - Network
      - Cards
      - Notes
    * - quorra1
      - 2x `AMD EPYC 7502 (Rome) <https://www.amd.com/en/products/cpu/amd-epyc-7502>`__
      - 256 DDR4, 3200 MHz, 16 GB DIMMs
      - Bluefield-2 NIC, 10 GE
      - 4x A30
      -       
    * - quorra2
      - 2x `AMD EPYC 7502 (Rome) <https://www.amd.com/en/products/cpu/amd-epyc-7502>`__
      - 256 DDR4, 3200 MHz, 16 GB DIMMs
      - Bluefield-2 NIC, 10 GE
      - 4x A30, 1x A100
      -
    * - rg-fpaa-host
      - Raspberry Pi Model 3B
      - 2 GB
      - 
      - 
      - Hosts FPAA via USB UART connection
    * - rudi1
      - 
      -
      -
      -
      - `Jetson Xavier NX Developer Kit <https://developer.nvidia.com/embedded/jetson-xavier-nx-devkit>`__
      
Reconfigurable and Novel Networking
-----------------------------------
	
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - CPU
      - Memory (GB)
      - Network
      - Cards
      - Notes
    * - flubber1
      - 2x `Intel E5-2630 <https://ark.intel.com/content/www/us/en/ark/products/92981/intel-xeon-processor-e5-2630-v4-25m-cache-2-20-ghz.html>`__
      - 256 DDR4, 2133 MHz, 32 GB DIMMs
      - 10 GE
      - 2x Alveo U50, Coral TPU
      - NA
    * - flubber2
      - 2x `Intel Gold 6226R <https://ark.intel.com/content/www/us/en/ark/products/199347/intel-xeon-gold-6226r-processor-22m-cache-2-90-ghz.html>`__
      - 384 DDR4, 2666 MHz, 32 GB DIMMs
      - 10 GE
      - Arria 10 PAC, Bittware 520N
      - NA
    * - flubber3
      - 2x `Intel Gold 6226R <https://ark.intel.com/content/www/us/en/ark/products/199347/intel-xeon-gold-6226r-processor-22m-cache-2-90-ghz.html>`__
      - 384 DDR4, 2666 MHz, 32 GB DIMMs
      - 10 GE, EDR IB 
      - Stratix 10 PAC, Bittware 520MX, Bittware 385A-SoC 
      - NA
    * - flubber4
      - 2x `AMD EPYC 7513 (Milan) <https://www.amd.com/en/products/cpu/amd-epyc-7513>`__
      - 256 DDR4, 3200 MHz, 16 GB DIMMs
      - NVIDIA ConnectX-6 
      - NA
      - NA
    * - flubber5
      - 2x `AMD EPYC 7513 (Milan) <https://www.amd.com/en/products/cpu/amd-epyc-7513>`__
      - 256 DDR4, 3200 MHz, 16 GB DIMMs
      - NVIDIA ConnectX-6 
      - Xilinx Alveo U280
      - NA
    * - flubber6
      - 2x `AMD EPYC 7513 (Milan) <https://www.amd.com/en/products/cpu/amd-epyc-7513>`__
      - 256 DDR4, 3200 MHz, 16 GB DIMMs
      - NVIDIA ConnectX-6, Innova-2 Flex, `Bluefield-1 NIC <https://github.gatech.edu/crnch-rg/rogues-docs/wiki/%5BNetworking%5D-Mellanox-BlueField-Resources>`__, Bluefield-2 NIC, Intel N6000 
      - NA 
      - Smart Networking Node
    * - flubber7
      - 2x `AMD EPYC 7513 (Milan) <https://www.amd.com/en/products/cpu/amd-epyc-7513>`__
      - 256 DDR4, 3200 MHz, 16 GB DIMMs
      - NVIDIA ConnectX-6, Innova-2 Flex, `Bluefield-1 NIC <https://github.gatech.edu/crnch-rg/rogues-docs/wiki/%5BNetworking%5D-Mellanox-BlueField-Resources>`__, Bluefield-2 NIC, Intel N6000 
      - NA
      - Smart Networking Node
    * - flubber8
      - 2x `Intel Gold 6338 <https://www.intel.com/content/www/us/en/products/sku/212285/intel-xeon-gold-6338-processor-48m-cache-2-00-ghz/specifications.html>`__
      - 512 DDR4, 3200 MHz, 32 GB DIMMs
      - NVIDIA ConnectX-6
      - NA 
      - NA
    * - flubber9
      - 2x `Intel Gold 6338 <https://www.intel.com/content/www/us/en/products/sku/212285/intel-xeon-gold-6338-processor-48m-cache-2-00-ghz/specifications.html>`__
      - 512 DDR4, 3200 MHz, 32 GB DIMMs
      - NVIDIA ConnectX-6
      - NA 
      - NA
    * - flubber10
      - 2x `Intel Gold 6338 <https://www.intel.com/content/www/us/en/products/sku/212285/intel-xeon-gold-6338-processor-48m-cache-2-00-ghz/specifications.html>`__
      - 512 DDR4, 3200 MHz, 32 GB DIMMs
      - NVIDIA ConnectX-6
      - NA 
      - NA
      
Devboard Hosts
--------------------   
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1
    
    * - Resource
      - CPU
      - Memory (GB)
      - Network
      - Cards
      - Notes
    * - brainard2
      - i5-10210U
      - 32 GB DDR4, 2666 MHz, 16 GB DIMMs
      - 1 GE
      - 
      - Connection to RISC-V board and FPGA, `Intel NUC10i5FNK <https://www.intel.com/content/www/us/en/products/sku/195507/intel-nuc-10-performance-kit-nuc10i5fnk/specifications.html>`__
      
RISC-V
--------------------   
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - CPU
      - Memory (GB)
      - Network
      - Notes
    * - johnny-rv5-1
      - 4xU74 cores and 1xS7 core, 1.4 GHz
      - 16 GB DDR4
      - 1 GE
      - SiFive Unmatched motherboard

Simulation and Tutorial Machines
--------------------------------
	
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - CPU
      - Memory (GB)
      - Network
      - Notes
    * - hawksbill / notebook
      - 4x `Intel E7-4820 <https://ark.intel.com/content/www/us/en/ark/products/53675/intel-xeon-processor-e74820-18m-cache-2-00-ghz-5-86-gts-intel-qpi.html>`__
      - 1024 DDR3
      - 1 GE
      - Used for Jupyter notebooks
 
Techfee Systems
===============
.. list-table:: 
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Resource
      - CPU
      - Memory (GB)
      - Network
      - Cards
      - Notes
    * - frozone<1-4>
      - 2x `Ice Lake 8352Y <https://www.intel.com/content/www/us/en/products/sku/212284/intel-xeon-platinum-8352y-processor-48m-cache-2-20-ghz/specifications.html>`__
      - 256 DDR4, 3200GHz, 16 GB DIMMs
      - `Omni-Path 100 GB, 100HFA16LS <https://ark.intel.com/content/www/us/en/ark/products/92007/intel-omni-path-host-fabric-interface-adapter-100-series-1-port-pcie-x16.html>`__
      - `1.6TB P5800X SSD <https://www.intel.com/content/www/us/en/products/sku/201859/intel-optane-ssd-dc-p5800x-series-1-6tb-2-5in-pcie-x4-3d-xpoint/specifications.html>`__ 
      - FY 2021 TechFee Acquisition
