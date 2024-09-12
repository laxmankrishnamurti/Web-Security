# How the Internet works?

This is the crucial stage for any web security engineers to understand the basics and underlying concepts of web technologies and its' protocols. We must have knowledge about how computers exchange data over the web.

PREDECESSOR OF THE INTERNET ===> ARPANET (Advanced Research Projects Agency Network).

## TCP(Transmission Control Protocol).

The first message sent over the "ARPANET" was a LOGIN command destined for a remote computer at Stanford University. The network sent the first two letters, <code>LO</code> and then crashed. This was a problem for US military, which was looking for a way to connect remote computers so that they could continue to exchange information at any situation.

To address this problem, the network engineers developed the "Transmission Control Protocol(TCP)" to ensure a reliable exchange of information between computers.

## How data travels on the Internet?

When a computer sends a message to another machine via TCP, the message is split into data packets that are send towards their eventual destination with a destination address. If the recipient fails to acknowledge receipt of a packet, the sender resends that packet, possibly along a different network path. In this way, TCP allows computers to deliver data across a network that is expected to be unreliable.

TCP has undergone significant improvements as the internet has grown. Packets are now send with a "checksum" that allows recipients to detect data corruption and determine whether packetes need to be resent.

Sendersa also preemptively adjust the rate at which they send data according to how fast it's being consumed. Because Internet servers are usually magnitudes more powerful than a client that receive their messages, so they need to be careful not to overwhelm the client's capacity.

TCP(Transmission Control Protocol) ===> Delivery Guarantees. (Mostly used protocol in web).
UDP(User Datagram Protocol) ===> Data packets could be lost. (Mostly used in streaming live video.)

## IP(Internet Protocol) Addresses

Data packets on the internet are sent to Internet Protocol(IP) addresses, numbers assigned to individual internet-connected computers. Each IP address must be unique, so new IP addresses are issued in a structured fashion.

Highest Level Authority ===> ICANN(Internet Corporation for Assigned Names and Numbers)
Regional Authorities ===> Grants the blocks of addresses.
ISPs and Hosting Companies ===> Provides IP addresses to each and every single computer, servers or mobile devices that are connected to the internet.

IP addresses are binary numbers, generally written in IP version 4(IPv4) syntax, which allows for 2^32 (4,294,967,296) addresses.

### Let's understand about Memory addresses.

Helper :: ChatGPT

#### Q :: What does it mean by a 32 bit processor or 64 bit processor can process 32bit or 64bit of data at once? Is there any relationship between memory address?

1. Data width

   - A 32-bit processor has registers (small storage units in the CPU) that are 32 bits wide. This means the processor can process, calculate, or move 32 bits of data (4 bytes) at a time.
   - A 64-bit processor has registers that are 64 bits wide, allowing it to process 64 bits of data (8 bytes) in a single clock cycle.
   - This ability to handle more data at once makes 64-bit processors more efficient, especially in tasks that involve large numbers or high data throughput.

2. Relationship to Memory Addresses
   - A memory address is a reference to a specific location in RAM, and each address is a unique identifier for storing data.
   - A 32-bit processor uses 32-bit memory addresses, meaning it can reference 2^32 unique memory locations. Since each memory location typically represents one byte, a 32-bit system can address a maximum of 4 GB of RAM (around 4.29 billion addresses).
   - A 64-bit processor uses 64-bit memory addresses, meaning it can reference 2^64 unique memory locations. This is an extremely large number, which theoretically allows a 64-bit system to address up to 18.4 quintillion bytes of RAM, though practical limits are much lower (most modern systems support up to hundreds of gigabytes or a few terabytes of RAM).

#### Q :: What is a memory address? is this is just a transistor that holds 0 or 1? tell me what exactly a memory address is? Do both RAM and CPU has memeory addresses or something else?

A memory address is a unique identifier used to access a specific location in a computer’s memory (RAM). It is not a physical object like a transistor, but rather a conceptual way of referring to locations where data is stored. Let's break it down in detail:

<code>What Exactly is a Memory Address?</code>

A memory address is like a "house number" for memory cells in RAM. Each cell in memory can hold a small piece of data, typically one byte (8 bits). The memory address serves as a label to locate that particular byte of data so the system knows where to store or retrieve information.

<code>How Memory Addresses Work:</code>

1. RAM(Random access memory)

   - RAM is made up of millions or billions of memory cells. Each cell can store a single bit (0 or 1), and groups of 8 bits form a byte.
   - Each byte in memory has a unique address so the CPU can read from or write to that location.
   - For example, if a program needs to store the number "100," it might place it in memory at address 0x1A3F. Later, if the program wants to retrieve that number, it accesses memory address 0x1A3F to get the data.
   - Memory addresses are managed as numbers, often written in hexadecimal (base 16) because it’s compact and human-readable.

2. CPU and Memory Addresses
   - The CPU doesn't store data like RAM does, but it uses registers (small, fast storage locations) to temporarily hold data that it's processing.
   - When the CPU needs data, it will issue a memory address to the memory controller, which directs the CPU to the correct location in RAM. The address refers to the location in RAM where the data is stored.

<code>The Role of Transistors</code>

1. While transistors are fundamental building blocks of memory, a memory address is a higher-level abstraction.
2. Transistors in RAM or other memory technologies form the physical circuitry that holds the actual binary data (0s and 1s).
   - In DRAM (Dynamic RAM), each memory cell is made of a transistor and a capacitor. The capacitor stores a charge (representing 1) or no charge (representing 0), and the transistor acts as a switch to control access to that charge.
   - However, a memory address is simply the number used to refer to these cells.

<code>Analogy</code>

1. Imagine a library:
   - The library is like your RAM, with thousands of shelves (memory cells) holding books (data).
   - Each shelf has a number (memory address) so you can locate it easily.
   - When you want to find a book (retrieve data), you don’t look through every shelf — you use the number (memory address) to go directly to the right spot.

#### Q :: What does it mean by 32bit or 64bit memory address? 4GB RAM means there are 4.2 billions of cell are available. And the memory address is not like a permanent number it is automatically generated by operating system's memory controller. And whenever data needs to be stored in RAM the memory controller generates a dynamic memory address and assign it to a cell and stored the value in that particular memory address. And whenever CPU needs to access the data it will go to the memory controller and ask for a memory address to that particular data and retrieve those data from the cell or from that particular memory address and then it holds the data into its' capacitor and CPU use the data to run the program. amd i right? or there is any mistake what i'm doing to understand it properly?

<code>Clarifying Your Understanding:</code>

1. Memory Addresses are Fixed for Data in RAM:

   - Memory addresses are not dynamically generated every time data is stored. The memory controller manages fixed physical addresses for each memory cell (byte) in RAM.
   - When a program needs to store data, the operating system (OS) allocates a specific fixed memory address for that data. The data stays at that address until the program finishes or no longer needs that data, and only then is the memory freed for reuse.

2. Addressing RAM Cells:

   - Each byte in RAM already has a predefined, fixed address. For example, the first byte of RAM is at address 0x00000000 (in a 32-bit system), and the last byte in a 4 GB system is at 0xFFFFFFFF.
   - When the CPU or a program requests to store or retrieve data, it refers to these fixed memory addresses.

3. Dynamic Allocation (Virtual Memory):

   - While physical memory addresses are fixed, the operating system creates virtual memory addresses for programs. These virtual addresses map to the actual physical memory addresses, allowing the OS to manage memory more flexibly.
   - Virtual memory helps isolate processes from each other and ensures efficient memory usage, especially when you have limited RAM.

4. Memory Controller and CPU Interaction:

   - When a program requests to store or access data, the CPU interacts with the memory controller.
   - The CPU issues a memory address to the memory controller, which then retrieves or stores data in the corresponding location in RAM. The CPU doesn't ask the memory controller to "generate" an address—it directly provides the address where the data is or where it needs to be written.

5. CPU Registers and Cache:
   - The CPU temporarily holds data in registers (very fast memory units within the CPU) when performing calculations. It doesn’t use capacitors directly to store data in the way you described—capacitors are more relevant to how RAM (specifically DRAM) stores data.
   - CPU Cache is a smaller, faster memory that temporarily holds frequently used data, reducing the time needed to access RAM.

<code>Correcting Your Understanding:</code>

    - Memory addresses are not dynamically generated each time data is stored; they are predefined for every byte in RAM. The operating system assigns existing memory addresses to the program, and the memory controller simply manages the traffic between the CPU and the correct memory address.
    - Memory address allocation for a program is managed by the operating system, often using virtual memory to map program-specific addresses to the real, physical memory addresses in RAM.
    - The CPU does not store data in capacitors directly. Capacitors are part of how DRAM (Dynamic RAM) stores data, but the CPU itself uses registers and cache for short-term data handling.

<code>How Data is Stored and Retrieved:</code>

1. When Storing Data:

   - The operating system allocates a memory address for the data and stores it at that fixed address in RAM.
   - The memory controller manages the movement of data between RAM and the CPU but doesn't generate new memory addresses.

2. When Retrieving Data:
   - The CPU issues a request to the memory controller with the specific memory address where the data is stored.
   - The memory controller accesses the corresponding memory cell in RAM and sends the data back to the CPU.

<code>Example :: </code>

- Suppose your system has 4 GB of RAM and is 32-bit:
  - The CPU might request to store a piece of data, like an integer, at a specific memory address (e.g., 0x1A2B3C4D).
  - The memory controller takes that address and places the data in the corresponding location in RAM.
  - Later, if the CPU needs that data again, it will reference the same memory address (0x1A2B3C4D) and retrieve the data from that exact spot in RAM.

<code>Summary of Key Points:: </code>

- Memory addresses are fixed and predefined for every byte in RAM.
- The operating system assigns memory addresses to programs using virtual memory, and these addresses map to physical RAM.
- The CPU interacts with the memory controller to access data stored at specific memory addresses.
- Capacitors are used in RAM (specifically DRAM) to store bits (0 or 1), but the CPU itself uses registers and cache for short-term data storage and processing.

#### Q :: Relationship Between Cells, Bytes, and Memory Addresses.

<code>Cells in RAM</code>

1. What is a RAM Cell?

   - A cell in RAM is the smallest unit of memory storage.
   - Each cell can store a single bit of data, which is either a 0 or a 1.
   - In DRAM (Dynamic Random Access Memory), each cell is typically made up of a capacitor (which holds the charge representing a 0 or 1) and a transistor (which acts as a switch to control access to that charge).

2. Grouping Bits into Bytes:
   - 8 bits = 1 byte.
   - A byte is a unit of digital information that consists of 8 bits. This means every 8 cells (each storing a bit) collectively store 1 byte of data.
   - 1 byte can represent 256 possible values (2⁸ = 256), ranging from 0 to 255.

<code>How RAM Capacity is Measured</code>

When we talk about the capacity of RAM, like 4 GB (gigabytes) of RAM, it refers to the total amount of data that the RAM can hold. Here's the relationship:

    - 4 GB RAM = 4 gigabytes of memory.
    - 1 GB = 1,073,741,824 bytes (2³⁰ bytes).
    - 4 GB = 4 × 1,073,741,824 bytes = 4,294,967,296 bytes.

This means that in a 4 GB RAM system, the RAM can store about 4.29 billion bytes of data. Since 1 byte = 8 bits, the total number of bits (or individual memory cells) in a 4 GB RAM system is:

    - 4.29 billion bytes×8 bits per byte=34.36 billion bits.

So, a 4 GB RAM system has 34.36 billion individual memory cells (since each cell stores 1 bit), but these cells are grouped into about 4.29 billion bytes, with each byte having a unique memory address.

<code>How they work together?</code>

1. 1 Byte = 8 Cells:

   - Each memory address refers to 1 byte (8 bits), not to an individual bit.
   - In a 4 GB RAM system, there are 4.29 billion memory addresses, each referring to a different byte of data. Each of these bytes is made up of 8 cells (8 bits), and the CPU reads or writes data to these addresses in chunks of 1 byte or more.

2. Memory Addressing:
   - Each memory address corresponds to a byte in memory, and that byte contains 8 bits (each bit stored in a separate cell).
   - So, when the CPU accesses memory, it is asking for data from a specific memory address. For example, if the CPU asks for data from memory address 0x123456, it will retrieve the 8 bits stored at that address, which are spread across 8 individual memory cells.

<code>What Does "4 GB RAM" Really Mean?</code> - When you say you have 4 GB of RAM, it means your system has the capacity to store 4.29 billion bytes of data. - Since each byte is made up of 8 bits, this translates to 34.36 billion individual memory cells in the RAM, each storing a single bit (either 0 or 1). - The 4.29 billion bytes are organized in such a way that each byte has its own unique memory address. The CPU uses these addresses to locate where data is stored in RAM.

<code>Visual Analogy</code>

Imagine a massive storage warehouse with 4.29 billion boxes. Each of these boxes can hold a small object (1 byte), and inside each box, there are 8 smaller compartments (cells), each capable of holding either a 0 or 1 (a bit). Each box (byte) has a label (a memory address), and the CPU uses these labels to locate the box it needs to access. - Box (Byte) = Contains 8 compartments (bits). - Memory Address = Label that identifies the box. - 4.29 billion boxes = The amount of data your 4 GB RAM can store.

<code>SUMMARY</code>

- RAM cells are the smallest units of memory, each storing 1 bit (either 0 or 1).
- 8 bits = 1 byte, and each byte has a unique memory address.
- In a 4 GB RAM system, there are 4.29 billion bytes (each byte containing 8 bits or 8 cells), which means the RAM has a total of 34.36 billion individual cells.
- The memory addresses refer to bytes (not individual bits), and the CPU accesses memory using these addresses to retrieve data.

#### Q :: It means the cell is spread like a mesh in the RAM?

Yes, we can think of the cells in RAM being arranged in a grid-like structure or mesh, where each cell holds a single bit (0 or 1), and groups of 8 cells form a byte. Each byte is what the CPU addresses directly using a memory address.

<code>Visualizing the RAM Structure::</code>

1. Grid or Mesh Layout:

   - Imagine the memory in RAM as a large grid or mesh.
   - Each square in this grid is a cell that holds 1 bit (either 0 or 1).
   - 8 cells in a row form 1 byte, and the memory address refers to this group of 8 cells (i.e., 1 byte).

2. Addressing:
   - The operating system assigns a unique memory address to each group of 8 cells (1 byte). The memory controller and the CPU then use these addresses to access and manage data in the RAM.
   - The layout may physically appear like a mesh or grid of cells on the RAM chip, but the memory addresses abstract away that physical structure for the CPU and software to use.

<code>RAM Cell Organization (Mesh-like Concept)::</code>

- Physical Organization: In reality, the cells are physically laid out in rows and columns (like a matrix) on the RAM chip. However, the exact layout depends on the specific type of RAM (e.g., DRAM).
- Logical Organization: From the CPU's perspective, the RAM looks like a continuous, sequential line of memory addresses, where each address points to 1 byte (8 cells).

#### Q :: The concept of grouping 8bits into 1 byte is done by RAM or Memory Controller? What are the Component of RAM that form a cell or Byte(if RAM does the work)?

Great question! The grouping of 8 bits into 1 byte is more of a logical convention that is standardized across most computing systems. The actual process of accessing data in bytes (8-bit chunks) is handled by the memory controller and the CPU, but the RAM itself stores bits at the hardware level. Let me explain this step by step.

1. Who Groups 8 Bits into 1 Byte?
   - RAM is responsible for storing bits (0s and 1s) in memory cells.
   - The memory controller and CPU handle reading and writing in chunks of 1 byte (8 bits), or larger, based on the instructions they receive.

The RAM doesn’t do any "grouping" itself. Instead:

- RAM stores individual bits in memory cells.
- When data needs to be accessed or manipulated, the memory controller and CPU treat data in terms of bytes (or larger units, like 2, 4, or 8 bytes at a time, depending on the system architecture).

This grouping of 8 bits into a byte is done based on how the CPU and memory controller communicate with the RAM, and this is a fundamental aspect of how modern systems are designed. The 8-bit byte is a standard unit, but some operations may even access memory in larger chunks (e.g., 32 bits or 64 bits at once, depending on the system architecture).

2. Components of RAM that Form a Cell or Byte

At the hardware level, each memory cell in RAM is responsible for storing a single bit of data. Let’s break down how this works in Dynamic RAM (DRAM), the most common type of RAM.

<code>Components of a RAM Cell::</code>

A single bit of data is stored in each cell in DRAM. Each cell consists of:

1.  Capacitor:

    - A capacitor is used to store the charge that represents a bit.
    - A fully charged capacitor typically represents a 1, and a discharged capacitor represents a 0.

2.  Transistor:
    - The transistor acts as a switch that controls whether the capacitor’s charge can be accessed or changed.
    - The CPU or memory controller can read from or write to the capacitor via the transistor.

In Static RAM (SRAM), which is faster but more expensive and typically used for cache, the memory cell consists of multiple transistors instead of capacitors, which hold the state of the bit without needing to be refreshed like DRAM does.

<code>Formation of a Byte in RAM::</code>

- 8 bits are stored across 8 cells in RAM, where each cell contains one bit.
- These 8 cells are treated as a single byte when accessed by the CPU or memory controller, but at the hardware level, they are just individual bits stored in separate cells.
- The memory controller ensures that when the CPU requests data, it retrieves and groups the corresponding 8 bits together to form a byte.

3. Role of the Memory Controller:

The memory controller (often integrated into the CPU these days) manages how data is read from or written to RAM. When the CPU requests data:

- The memory controller accesses RAM by addressing each byte.
- It retrieves or writes 8 bits at a time (or more, depending on the operation) from the corresponding 8 cells in RAM and presents them as a byte to the CPU.

<code>RAM and Byte Formation Process::</code>

1. RAM Cells Store Bits: Each RAM cell stores a single bit of data, using a capacitor and transistor (in DRAM).
2. Memory Controller Groups Bits: The memory controller logically groups 8 bits from 8 adjacent cells to form a byte when requested by the CPU.
3. CPU Interacts in Bytes or Larger: The CPU typically works with data in bytes or larger units (like 32 or 64 bits, depending on the architecture).

<code>SUMMARY ::</code>

- RAM stores data as individual bits in cells. Each cell holds a single bit of data.
- The memory controller handles grouping these 8 bits together into a byte for the CPU to read or write.
- The physical components of a RAM cell include a capacitor and a transistor in DRAM, and multiple transistors in SRAM.
- RAM does not perform grouping—it is simply the storage medium. The memory controller and CPU manage data in terms of bytes and larger units.

This structure allows for efficient data storage and retrieval at the hardware level while adhering to the 8-bit byte standard used by most computing systems.

#### Q :: It means the RAM as we called the Main memory of the computer is nothing but a matrix in which each component is a cell that is build up with capacitor and transistor and hold charges (0 or 1) and controlled by transistor. and when CPU request for any particular data which is stored in the RAM cell the memory controller go to that place the CPU gives the address and it retrives the cell and formed into bytes format. Like let say if CPU request for a data which cannot adjust into a single byte let say the number 258. Then CPU gives an address (which is the memory address of 2 bytes in short 16bits in short 16 cells) to the memory controller and the memory controller retrive those 16bits or whatever the bit in which the number 258 can consist. and then it groups into 2 bytes and then send the data to the CPU. amd i right?

Yes, you're absolutely right! You've understood the concept well. Here's a detailed confirmation and breakdown of the process you just described:

<code>RAM as a Matrix of Cells::</code>

- RAM (main memory) can indeed be thought of as a large matrix (grid-like structure) where each individual element is a memory cell.
- Each memory cell consists of:
  - A capacitor that holds the charge, representing either a 0 (no charge) or 1 (charged).
  - A transistor that controls access to the capacitor and determines when the stored bit can be read or written.

These cells are arranged in rows and columns, making up the entire memory space.

<code>When the CPU Requests Data from RAM::</code>

1. Memory Address::

   - When the CPU requests data, it sends a memory address to the memory controller. This address tells the memory controller where to go in the RAM matrix to fetch the required data.

2. Accessing the Cells::
   - The memory controller uses this address to locate the specific bytes (which are made up of 8 cells per byte) where the data is stored.
   - If the requested data is larger than a single byte (e.g., the number 258), the memory controller will retrieve multiple bytes (in this case, 2 bytes, because 258 requires 16 bits, which is 2 bytes).

<code>Example with the Number 258::</code>

- The number 258 in binary is represented as 00000001 00000010, which is 16 bits long (or 2 bytes).
- Here's how it works:
  1. The CPU sends a request for the number 258 and gives the memory address that points to where this data is stored in RAM.
  2. The memory controller identifies that the number requires 2 bytes (or 16 bits), so it fetches data from two memory addresses (since each address points to 1 byte).
  3. The memory controller retrieves the 16 bits from RAM, grouping them into 2 bytes.
  4. The memory controller then sends these 2 bytes (which contain the value 258) back to the CPU.

<code>Summary of the Process::</code>

- RAM is a matrix of cells, where each cell stores a bit (0 or 1) using capacitors and transistors.
- When the CPU requests data (like the number 258), it sends the memory address to the memory controller.
- The memory controller retrieves the data from the corresponding cells in RAM based on the address.
- If the data requires more than one byte (like the 16-bit number 258), the memory controller retrieves multiple bytes (2 bytes in this case), groups them, and sends them to the CPU.
