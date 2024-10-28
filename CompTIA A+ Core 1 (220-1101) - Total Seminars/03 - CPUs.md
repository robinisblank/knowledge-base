# CPUs

## What is a CPU?
- CPU stands for Central Processing Unit.
- Instead of saying that a CPU is the "brain" of a computer, it's more accurate to say that it's an incredibly powerful calculator.
- Every CPU has internal features to process commands.
- A register is a memory location inside a CPU.
- The CPU has an internal code book that identifies each instruction pattern.
- Each CPU can only execute instructions written in its specific machine language. Different types of CPUs have different instruction sets, and these instruction sets define the machine language for that CPU.
- The external data bus is the set of wires that carry data and instructions between the CPU and RAM.
- Clock is like a switch that when pressed tells the CPU to do something.
- CPU utilizes pipelines to optimize the processing of commands. It has many units like prefetch, integer math, long numbers, cache etc. The number of steps depends on the manufacturer of the CPU.

## Modern CPUs
- The capability of a CPU is measured by its clock speed and the number of cores it has.
- Clock speed is the number of tasks that a CPU can do per second.
- 1 hertz (Hz) = 1 cycle of tasks per second
- 1 megahertz (MHz) = 1 million cycles per second
- 1 gigahertz (GHz) = 1 billion cycles per second
- In modern CPUs, clock speed is measured in GHz.
- Cores are multiple processors on a single chip.
- Single-core means that there is only one information lane from which data can travel.
- Dual-core means that there are two information lanes from which data can travel.
- Quad-core means that there are four information lanes from which data can travel.
- Multi-core means more than one or multiple cores. It doesn't ends on the quad-core, modern CPUs can have much more than that.
- Advanced RISC Machine (ARM) is a CPU that works on the Reduced Instruction Set Computer (RISC) methodology. It is found in IoT devices or the newer apple products.
- Accelerated Processing Unit (APU) is a CPU with graphics processor embedded in it.
- CPU-Z is a software that provides information about the components like processor, motherboard and RAM.

## 32-Bit vs. 64-Bit Computing
- x86 or 32-bit system can handle data in 2<sup>32</sup> bits.
- x64 or 64-bit system can handle data in 2<sup>64</sup> bits.
- x86, x86-64, x64, and IA-32 are all Instruction Set Architecture (ISA) standards.
- x86 is only compatible with 32-bit hardware/software.
- x64 is only compatible with 64-bit hardware/software.
- x86-64 system is 64-bit primarily, but also supports 32-bit hardware/software.
- IA-32 is an acronym for Intel Architecture 32-bit.
- Almost all modern hardware and software supports 64-bit systems and are backwards compatible with 32-bit systems.
- x64 systems offer better security, graphics performance and data handling.

## Choosing the Right CPU
- Questions to consider:
	- What type of system do you want?
	- What's the primary use of the computer?
	- How long do you want this system to last?
- [PCPartPicker](https://pcpartpicker.com/) is a very useful site when building a PC.
- CPUs designed for laptops come with features to help with power consumption and battery usage.
- Higher-end CPUs offer more cores and a faster clock speed.
- CPUs with extra cores benefit intensive tasks such as 3D gaming and video editing.
- Some CPUs are unlocked and can be overclocked.

## CPU Generations and Architecture
- The higher the CPU's tier, the better its performance.
- The generation is the indicator of the CPU's age.
- The model refers to the performance of the CPU within a generation. If two CPUs have the same model, then the CPU with the higher generation is better.
- Different suffixes used by different brands have different meanings. For example, in Intel, "K" means that the CPU is unlocked and can be overclocked, and "F" means that the CPU has no integrated graphics. In AMD, "X" means that the CPU is slightly overclocked by default, and "G" means that the CPU includes integrated graphics.
- Examples:
	- Intel Core i9 12900K -> Here "Intel" is the brand, "Core i9" is the tier, "12" is the generation, "900" is the model, and "K" is the suffix.
	- AMD Ryzen 9 5900X -> Here "AMD" is the brand, "Ryzen 9" is the tier, "5" is the generation, "900" is the model, and "X" is the suffix.
- There are many websites that provide detailed information about a CPU and its preceding generations.

## CPU Cooling
- Overheating can cause issues like system instability and intermittent shutdowns.
- Heat sinks use metal fins and pipes to passively transfer heat. A fan is used together that pushes the heat out of the system.
- Thermal paste comes in silicon-based, ceramic-based, carbon-based, metal-based, and liquid metal-based.
- Thermal paste and pads are used to fill in gaps and provide better thermal conductivity between the CPU and heat sink.
- [How to Apply Thermal Paste and How it Works](https://www.intel.com/content/www/us/en/gaming/resources/how-to-apply-thermal-paste.html)
- Liquid cooling has better thermal transfer capabilities than air cooling.

## Installing and Troubleshooting a CPU
- Make sure to use Electrostatic Discharge (ESD) protection.
- Handle sensitive equipment carefully.
- Intel CPUs use Land Grid Array (LGA).
- AMD CPUs use Pin Grid Array (PGA).
- The Zero-Insertion Force (ZIF) mechanism is used to secure the CPU into the motherboard's socket.
- The orientation notch identifies which direction the CPU should face so that it seats correctly in the socket.
- When troubleshooting a non-functional CPU, first check all connections and make sure that the fan, heat sink, and the CPU itself is seated properly before proceeding.
- Refer to the vendor's instructions for guidance. Never throw away those manuals while unboxing stuff.