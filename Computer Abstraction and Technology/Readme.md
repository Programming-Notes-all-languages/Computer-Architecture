<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#abstraction-in-computer-architecture'>Abstraction in Computer Architecture</a>
  </li>
  <li>
    <a href='#eight-great-ideas'>Eight Great Ideas</a>
  </li>
  <li>
    <a href='#components-of-a-computer'>Components of a Computer</a>
  </li>
  <li>
    <a href='#performance-factors'>Performance Factors</a>
  </li>
</ol>
</details>

## Abstraction in Computer Architecture
<em>Abstraction</em> manages complexity by hiding lower-level details

Key abstraction layers:
<ul>
  <li><em>Instruction Set Architecture (ISA)</em>
    <ul>
      <li>Interface between hardware and software</li>
      <li>Defines instructions, registers, memory model, and input/output behavior</li>
    </ul>
  </li>
  <li>Implementation of an ISA (Microarchitecture)
    <ul>
      <li>The different components like the ALU, registers, etc. the define the ISA in hardware</li>
    </ul>
  </li>
  <li>Implementation Level of the Microarchitecture (RTL)
    <ul>
      <li>How all the components of the microarchitecture are connected</li>
    </ul>
  </li>
</ul>

## Eight Great Ideas
<ol>
  <li>Design for <em>Moore's Law</em>
    <ul>
      <li>Moore's Law states that the number of transistors on an integrated circuit doubles about every 18 to 24 months, while the cost of each of the transistors gets cheaper. Computer architects use this to advance CPU integrated circuits performance while enhancing power efficiency and maintaining the same instruction set architecture</li>
      <li>A <em>transistor</em> is an electrical shift that controls electrical currents. The predecessor to transistors were vacuum tubes, yet transistors are much more efficient in most aspects, regarding economics, heat output, and relative performance. The fabrication of transistors has facilitated the world's pace against Moore's Law. Integrated circuits are becoming more powerful, smaller, and cheaper as a result</li>
    </ul> 
  </li>
  <li>Use abstraction to simplify design
    <ul>
      <li>Abstraction is the idea of hiding complexity from the lower-levels of the computer from the upper-levels closer to the software. This principle is part of the eight great ideas because it manages complexity at each stage of a computer. Computer designers can work on their level of a computer more easily as abstraction hides the intricate details of the lower-levels in the computer</li>
    </ul>
  </li>
  <li>Make the common case fast</li>
  <li>Performance via parallelism</li>
  <li>Performance via pipelining</li>
  <li>Performance via prediction</li>
  <li>Hierarchy of memories</li>
  <li>Dependability via redundancy</li>
</ol>

## Components of a Computer
<ul>
  <li><em>Input/Output</em>
    <ul>
      <li>Display, keyboard, mouse</li>
      <li>Storage devices like hard disks, flashes, CD</li>
      <li>Network adapters</li>
    </ul>
  <li><em>Processor</em>
    <ul>
      <li>Datapath performs operations on data</li>
      <li>Control sequences datapath and memory</li>
      <li>Cache memory
        <ul>
          <li>Small fast SRAM memory for immediate access to data</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>

## Performance Factors
<ul>
  <li><em>Algorithm</em> determines the number of operations executed</li>
  <li><em>Programming language, compiler, architecture</em> determine the number of machine instructions executed per operation</li>
  <li><em>Processor and memory system</em> determine how fast instructions are executed</li>
  <li><em>I/O System</em> determines how fast input/output operations are executed</li>
</ul>

### Defining Performance
There are two main metrics:
<ul>
  <li><em>Response time</em> is the time to complete a task</li>
  <li><em>Throughput</em> is the number of tasks completed per unit of time</li>
</ul>

Faster CPUs have a better response time and more CPUs have higher throughput

<em>Relative performance</em> is where performance = 1 / execution time

### Measuring Execution Time
<ul>
  <li>Elapsed time is the total response time, including all aspects like processing, input/output, OS overhead, and idle time. This determines system performance</li>
  <li>CPU time is the time spent processing a given job</li>
</ul>

#### CPU Time Formula
CPU time = CPU clock cycles * clock cycle time = CPU clock cycles / clock rate

Performance is improved by:
<ul>
  <li>Reducing number of clock cycles</li>
  <li>Increasing clock rate</li>
</ul>

#### Instruction Count and Clock Cycles per Instruction (CPI)
Clock cycles = instruction count * cycles per institution

CPU time = instruction count * CPI * clock cycle time = (instruction count * CPI) / clock rate

<ul>
  <li><em>Instruction count</em> refers to the total number of machine instructions executed by a program. This is impacted by the instruction set architecture</li>
  <li><em>CPI (cycles per instruction)</em> is the average number of clock cycles per instruction affected by cache performance</li>
  <li><em>Clock cycle time</em> is equal to the inverse of clock rate</li>
  <li><em>Clock rate</em> is the number of cycles per second (also known as the frequency) which is affected by power and thermals</li>
</ul>

<details>
    <summary>Example program</summary>

There are two computers: PC A has a cycle time of 250ps and a CPI of 2.0; PC B has a cycle time of 500ps and a CPI of 1.2. The ISA is the same. Which PC is faster and by how much
<ul>  
  <details>
    <summary>Output</summary>


CPU Time A: (ISA * 2 * 250) = 500 * ISA<br />
CPU Time B: (ISA * 1.2 * 500) = 600 * ISA<br />
CPU A is faster by 600 / 500 = 1.2
      </details>
    </ul>  
  </details>

<details>
    <summary>Example program</summary>

<ol type="a">
  <li>If Computer A executes a program in 14 seconds, and Computer B executes the same program in 21 seconds, how much faster is Computer A than Computer B</li>
  <li>There are many factors that could contribute to this difference in performance between the two systems. Describe two such factors</li>
</ol>
<ul>  
  <details>
    <summary>Output</summary>

<ol type="a">
  <li>CPU Time A = 14s<br />
  CPU Time B = 21s<br />
  
  21s / 14s = 1.5. Computer A is 50 percent faster than Computer B</li>
  <li>Since the instruction count is the same for both computers, as they each execute the same program, the CPI of Computer B is likely lower than Computer A's and the clock rate of Computer B could be higher than Computer A's</li>
</ol>
      </details>
    </ul>  
  </details>

#### Average CPI
Average CPI = $\sum$(Instruction Frequency * Cycles per Instruction)

  <details>
    <summary>Example program</summary>

Consider two different implementations of the same instruction set. There are three instruction types. M1 has a clock rate of 2GHz and M2 has a clock rate of 2.2GHz. The average number of cycles for each type of instruction, as well as their frequencies, are given below. Calculate the average CPI for each machine

| Instruction | M1 Cycles | M2 Cycles |
| ----------- | --------- | --------- |
| A           | 2         | 3         |
| B           | 3         | 2         |
| C           | 3         | 1         |

<ul>  
  <details>
    <summary>Output</summary>
Average CPI M1 = (2 * 0.6 + 3 * 0.3 + 3 * 0.1) = 2.4<br />

Average CPI M2 = (3 * 0.6 + 2 * 0.3 + 1 * 0.1) = 2.5
      </details>
    </ul>  
  </details>

  <details>
    <summary>Example program</summary>

Using the following table with the calculated average CPIs for both machines,

Average CPI M1 = (2 * 0.6 + 3 * 0.3 + 3 * 0.1) = 2.4<br />

Average CPI M2 = (3 * 0.6 + 2 * 0.3 + 1 * 0.1) = 2.5,

determine the relative performance if the following changes are made. Assume the clock frequency and IC remain constant: M1 has a clock rate of 2GHz and M2 has a clock rate of 2.2GHz.

| Instruction | M1 Cycles | M2 Cycles |
| ----------- | --------- | --------- |
| A           | 2         | 3         |
| B           | 3         | 2         |
| C           | 3         | 1         |

  <ol type="a">
    <li>Modify M1 by improving B-type instructions to a CPI of 2</li>
    <li>Modify M2 by improving A-type instructions to a CPI of 2</li>
  </ol>
<ul>  
  <details>
    <summary>Output</summary>
<ol type="a">
  <li>
CPU Time<sub>old</sub> = (IC * 2.4) / 2GHz

CPI M1<sub>new</sub> = (0.60 × 2) + (0.30 × 2) + (0.10 × 3) = 2.1

CPU Time<sub>new</sub> = (IC * 2.1) / 2GHz

CPU Time<sub>old</sub> / CPU Time <sub>new</sub> = 2.4 / 2.1 = 1.14

This modification made the computer 14% faster
  </li>
  <li>
  CPU Time<sub>old</sub> = (IC * 2.5) / 2.2GHz

CPI M2<sub>new</sub> = (0.60 × 2) + (0.30 × 2) + (0.10 × 1) = 1.9

CPU Time<sub>new</sub> = (IC * 1.9) / 2.2GHz

CPU Time<sub>old</sub> / CPU Time <sub>new</sub> = 2.5 / 1.9 = 1.32

This modification made the computer 32% faster
  </li>
</ol>
      </details>
    </ul>  
  </details>

<details>
    <summary>Example program</summary>

A compiler designer is trying to decide between two code sequences for a particular computer. The hardware designers have supplied the following facts:

<table border="1">
  <tr>
    <th>Class</th>
    <th>A</th>
    <th>B</th>
    <th>C</th>
  </tr>
  <tr>
    <td>CPI for class</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
  </tr>
  <tr>
    <td>IC in sequence 1</td>
    <td>2</td>
    <td>1</td>
    <td>2</td>
  </tr>
  <tr>
    <td>IC in sequence 2</td>
    <td>4</td>
    <td>1</td>
    <td>1</td>
  </tr>
</table>
<ul>  
  <details>
    <summary>Output</summary>
Sequence 1: IC = 2 + 1 + 2 = 5<br />
Clock Cycles: (2 * 1) + (1 * 2) + (2 * 3) = 10<br />
Sequence 2: IC = 4 + 1 + 1 = 6<br />
Clock Cycles: (4 * 1) + (1 * 2) + (1 * 3) = 9<br />

CPI = Clock Cycles / Instruction Count<br />
CPI 1: 10 / 5 = 2<br />
CPI 2: 9 / 6 = 1.5<br />
      </details>
    </ul>  
  </details>

<details>
    <summary>Example program</summary>

Compilers can have a profound impact on the performance of an application. Assume that for a program, compiler A results in a dynamic instruction count of 1.0E9 and has an execution time of 1.1 s, while compiler B results in a dynamic instruction count of 1.2E9 and an execution time of 1.5 s.

<ol type="a">
  <li>Find the average CPI for each program given that the processor has a clock cycle time of 1ns</li>
  <li>Assume the compiled programs run on two different processors. If the execution times on the two processors are the same, how much faster is the clock of the processor running compiler B’s code versus the clock of the processor running compiler A’s code</li>
</ol>
<ul>  
  <details>
    <summary>Output</summary>
<ol type="a">
  <li>CPU time = instruction count * CPI * clock cycle time<br />

  CPI (A) = 1.1 s / (1.0E9 * 1.0E-9 s) = 1.1<br />
  CPI (B) = 1.5 s / (1.2E9 * 1.0E-9 s) = 1.25<br />
  </li>
  <li>
  (1.0E9 * 1.1) / CRA<br />
  (1.2E9 * 1.25) / CRB<br />
  Clock rate B is (1.2E9 * 1.25) / (1.0E9 * 1.1) = 1.37x times faster than clock rate A 
  </li>
</ol>  
      </details>
    </ul>  
  </details>

#### Parallel Execution
When instructions execute in parallel, the clock frequency remains unchanged, but the effective CPI decreases because more instructions complete pre cycle

<details>
    <summary>Example program</summary>

A compiler designer is trying to decide between two code sequences for a particular computer. The hardware designers have supplied the following facts:

<table border="1">
  <tr>
    <th>Class</th>
    <th>A</th>
    <th>B</th>
    <th>C</th>
  </tr>
  <tr>
    <td>CPI for class</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
  </tr>
  <tr>
    <td>IC in sequence 1</td>
    <td>2</td>
    <td>1</td>
    <td>2</td>
  </tr>
  <tr>
    <td>IC in sequence 2</td>
    <td>4</td>
    <td>1</td>
    <td>1</td>
  </tr>
</table>

One particular implementation of this supports executing 2 instructions of type A in parallel. What is the maximum relative performance increase one can achieve with this implementation over a mod with a CPI of 2.1 and an original with a CPI of 2.4
<ul>  
  <details>
    <summary>Output</summary>

Clock Cycles: ((2 * 0.6) / 2) + (3 * 0.3) + (3 * 0.1) = 1.5<br />

<ol type="a">
  <li>Performance over mod: 2.1 / 1.5 = 1.4, 40% faster</li>
  <li>Performance over original: 2.4 / 1.5 = 1.6, 60% faster</li>
</ol>
      </details>
    </ul>  
  </details>

  <details>
    <summary>Example program</summary>

CPU-A has an average CPI of 1.3 and a clock rate of 1.2GHz. CPU-B has an average CPI of 2.1 and a clock rate of 2.5GHz. We have a program, foo.exe, that we wish to run. When compiled for CPU-A, the program has exactly 1x10<sup>6</sup> instructions
<ol type="a">
  <li>How many instructions would the program need to have when
compiled for CPU-B, so the execution time of the program is the
same on both systems</li>
  <li>If the programs had the same number of instructions on both
systems, what should the CPI of CPU-B be so that it takes 50% as
long as CPU-A to execute the program</li>
  <li>We expect foo.exe to take 5 seconds to run on CPU-C, but after
running it, it actually took 15 seconds! Name 2 factors that may have
caused this disparity between expected time and actual time</li>
</ol>
</ol>
<ul>  
  <details>
    <summary>Output</summary>

<ol type="a">
  <li>CPU Time A = (1.0E6 * 1.3) / 1.2GHz<br />
  (x * 2.1) / 2.5GHz = (1.0E6 * 1.3) / 1.2GHz<br />
  x = 1.29E6 instructions</li>
  <li>CPI (B) / F (B) = 0.5 * (CPI (A) / f (A))<br />
  CPI (B) = 0.5 * 1.3 * 2.5GHz * (1 / 1.2GHz) = 1.35</li>
  <li>There could have been more than expected memory latency and incorrect assumptions about the IC or the CPI of CPU-C</li>
</ol>
      </details>
    </ul>  
  </details>

### Power
Power = Capacitive load * Voltage<sup>2</sup> * Frequency<br />

Dynamic Power = P<sub>new</sub> / P<sub>old</sub><br />

<details>
    <summary>Example program</summary>

Suppose a new CPU has 85% of capacitive load of old CPU, 15% voltage and 15% frequency reduction. What is the impact on dynamic power
<ul>  
  <details>
    <summary>Output</summary>
P<sub>new</sub> = (C<sub>old</sub> * 0.85) * (V<sub>old</sub> * 0.85)<sup>2</sup> * (F<sub>old</sub> * 0.85)<br />

P<sub>old</sub> = C<sub>old</sub> * V<sub>old</sub> * F<sub>old</sub><br />

P<sub>new</sub> / P<sub>old</sub> = 0.52 
      </details>
    </ul>  
  </details>

### Amdahl's Law
Time<sub>improved</sub> = (Time<sub>affected</sub> / improvement factor) + Time<sub>unaffected</sub>

<ul>
  <li>Time<sub>improved</sub>: the updated time</li>
  <li>Time<sub>affected</sub>: the amount of time that benefits from the improvement</li>
  <li>Improvement Factor: how much faster the part becomes</li>
  <li>Time<sub>unaffected</sub>: the part of the program that does not improve at all</li>
</ul>

#### Speedup
Speedup = 1 / Time<sub>improved</sub>

<details>
    <summary>Example program</summary>

In a program multiply accounts for 80s out ot 100s. If we improve the multiply by a factor of 2, what is the overall performance improvement
<ul>  
  <details>
    <summary>Output</summary>
Time<sub>improved</sub> = (Time<sub>affected</sub> / improvement factor) + Time<sub>unaffected</sub><br />

Time<sub>improved</sub> = (80s / 2) + (100s - 80s) = 60s
      </details>
    </ul>  
  </details>

  <details>
    <summary>Example program</summary>

Suppose you have a machine that executes a program consisting of 50% floating point multiply, 30% floating point divide, and the remaining 20% are from other instructions. Management wants you to make the machine 2x faster. You can make the multiply operation 10x faster OR the divide operation 4x faster. Can you meet management’s goal by making ONE improvement? If so, which one?

<ul>  
  <details>
    <summary>Output</summary>

Time<sub>improved</sub> = (Time<sub>affected</sub> / improvement factor) + Time<sub>unaffected</sub><br />

<ol type="a">
  <li>Time<sub>improved</sub> = 0.5 / 10 + 0.5 = 0.55<br />
  Speedup = 1 / 0.55 = 1.82 which is not twice as fast</li>
  <li>Time<sub>improved</sub> = (0.3 / 4) + 0.7 = 0.775<br />
  Speedup = 1 / 0.775 = 1.29 which is not twice as fast<br />
  Management's goal cannot be met with either one of those improvements</li>
</ol>
      </details>
    </ul>  
  </details>

### Millions of Instructions Per Second (MIPS)
MIPS = Clock Rate / (CPI * 10<sup>6</sup>)<br />